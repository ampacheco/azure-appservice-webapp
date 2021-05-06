# App Service WebApp

````sh
# settings
az-group=mslearn-scale-rg
az-appservice-plan=mslearn-scale-plan
az-webapp=mslearn-scale-webapp
az-region=eastus
az-webapp-runtime=DOTNETCORE|3.1

az group create -n ${az-group} -l ${az-region}  # Group Creation
az appservice plan create -n ${az-appservice-plan} -g ${az-group} --sku S1

# az webapp list-runtimes 
az webapp create -n ${az-webapp} -g ${az-group} -r $"{az-webapp-runtime}"

# Deploy web app
az webapp deployment source config-zip --src webapp.zip -g ${az-group} -n ${az-webapp} help
````
