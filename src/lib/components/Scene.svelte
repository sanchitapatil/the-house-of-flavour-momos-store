<script>
	import { T } from '@threlte/core';
	import { useTask } from '@threlte/core';
	import { Float } from '@threlte/extras';

	let rotation = $state(0);
	let time = $state(0);

	useTask((delta) => {
		rotation += delta * 0.15;
		time += delta;
	});

	// Dynamic positioning for floating chalk doodles
	const chalkDoodles = [
		// Star 1 (Yellow)
		{ pos: [-3, 2, -2], color: '#f1c40f', scale: 0.6, speed: 1.5, type: 'star' },
		// Steam Loop (White)
		{ pos: [3, 1, -3], color: '#ffffff', scale: 0.8, speed: 1.2, type: 'steam' },
		// Spark 1 (Red)
		{ pos: [-2, -2, -4], color: '#e74c3c', scale: 0.5, speed: 2, type: 'spark' },
		// Star 2 (Green)
		{ pos: [4, -2, -2], color: '#2ecc71', scale: 0.5, speed: 1.8, type: 'star' },
		// Spice ring (Yellow)
		{ pos: [0, 3, -5], color: '#f1c40f', scale: 0.7, speed: 1, type: 'ring' }
	];

	// Generates a soft field of floating chalk dust particles
	const dustParticles = Array.from({ length: 40 }, () => ({
		x: (Math.random() - 0.5) * 12,
		y: (Math.random() - 0.5) * 8,
		z: (Math.random() - 0.5) * 6,
		speed: 0.05 + Math.random() * 0.1,
		size: 0.02 + Math.random() * 0.04
	}));
</script>

<T.PerspectiveCamera makeDefault position={[0, 0, 10]} fov={35} />

<!-- Soft ambient lighting to eliminate shiny plastic reflections -->
<T.AmbientLight intensity={0.8} />
<T.DirectionalLight position={[0, 5, 5]} intensity={0.5} />

<!-- Floating Chalk Doodles Group -->
<T.Group rotation.y={rotation * 0.5}>
	{#each chalkDoodles as d}
		<Float speed={d.speed} rotationIntensity={1} floatIntensity={1}>
			<T.Group position={d.pos}>
				{#if d.type === 'star'}
					<!-- 3D Star Outline using double wireframe octahedron -->
					<T.Mesh rotation.y={time * 0.5}>
						<T.OctahedronGeometry args={[d.scale, 0]} />
						<T.MeshBasicMaterial color={d.color} wireframe={true} opacity={0.6} transparent={true} />
					</T.Mesh>
					<T.Mesh rotation.y={time * 0.5 + 45}>
						<T.OctahedronGeometry args={[d.scale * 0.7, 0]} />
						<T.MeshBasicMaterial color={d.color} wireframe={true} opacity={0.4} transparent={true} />
					</T.Mesh>
				{:else if d.type === 'steam'}
					<!-- Steam loop representation using wireframe torus knot -->
					<T.Mesh rotation.x={time * 0.2}>
						<T.TorusKnotGeometry args={[d.scale * 0.6, 0.15, 64, 8, 2, 3]} />
						<T.MeshBasicMaterial color={d.color} wireframe={true} opacity={0.4} transparent={true} />
					</T.Mesh>
				{:else if d.type === 'spark'}
					<!-- 3D Spark sketch using tetrahedron -->
					<T.Mesh rotation.z={time * 0.8}>
						<T.TetrahedronGeometry args={[d.scale, 0]} />
						<T.MeshBasicMaterial color={d.color} wireframe={true} opacity={0.5} transparent={true} />
					</T.Mesh>
				{:else if d.type === 'ring'}
					<!-- Sketchy orbit ring -->
					<T.Mesh rotation.x={1.2} rotation.y={time * 0.3}>
						<T.TorusGeometry args={[d.scale, 0.05, 8, 24]} />
						<T.MeshBasicMaterial color={d.color} wireframe={true} opacity={0.5} transparent={true} />
					</T.Mesh>
				{/if}
			</T.Group>
		</Float>
	{/each}
</T.Group>

<!-- Soft floating chalk dust field -->
{#each dustParticles as p}
	<T.Mesh position={[p.x, p.y + Math.sin(time * p.speed) * 0.8, p.z]}>
		<T.DodecahedronGeometry args={[p.size, 0]} />
		<!-- High-transparency basic material for soft chalky dust look -->
		<T.MeshBasicMaterial color="#ffffff" transparent={true} opacity={0.25} wireframe={true} />
	</T.Mesh>
{/each}
