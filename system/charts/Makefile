update:
	rm -rf charts
	helm repo add mongodb https://mongodb.github.io/helm-charts
	helm repo update mongodb
	helm pull mongodb/community-operator --untar --untardir community-operator
