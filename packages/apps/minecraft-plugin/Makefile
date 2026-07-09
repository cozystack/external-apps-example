export NAME=minecraft-plugin
export NAMESPACE=external-minecraft-operator

include ../../../scripts/package.mk

.PHONY: generate
generate: ## Regenerate values.schema.json, README.md, and the ApplicationDefinition schema from values.yaml annotations
	cozyvalues-gen -v values.yaml -s values.schema.json -r README.md
	../../../scripts/update-appdef.sh $(NAME)
