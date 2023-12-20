# create_pv_and_pvc:
# 	@kubectl apply -f storage-class.yaml
# 	@kubectl apply -f pv-claim.yaml

deploy_ingress_and_rules:
	@kubectl apply -f ingress-class.yaml
	@kubectl apply -f ingress-rule.yaml

deploy_node_app:
	@kubectl apply =f node-app-deploymnt.yaml

get_kivana_credentials:
	@kubectl get secrets --namespace=default elasticsearch-master-credentials -ojsonpath='{.data.username}' | base64 -d
	@kubectl get secrets --namespace=default elasticsearch-master-credentials -ojsonpath='{.data.password}' | base64 -d

configure_fluntd:
	@kubectl apply -f fluentd-config.yaml
	@kubectl rollout restart daemonset/fluentd


