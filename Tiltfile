# Build
custom_build(
	# Name of the container image
	ref = 'config-service',
	# Command to build th container image
	command = './mvnw spring-boot:build-image -Ddocker.name=$EXPECTED_REF',
	# Files to watch that trigger a new build
	deps = ['pom.xml', 'src']
)

# Deploy
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])

# Manage
k8s_resource('config-service', port_forwards=['8888'])