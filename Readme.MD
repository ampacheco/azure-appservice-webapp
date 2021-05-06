# App Service WebApp

````sh
# settings

echo -e ${az_group:=mslearn-scale-rg}
echo -e ${az_appservice_plan:=mslearn-scale-plan}
echo -e ${az_webapp:=mslearn-scale-webapp}
echo -e ${az_region:=eastus}
echo -e ${az_webapp_runtime:=DOTNETCORE|3.1}

az group create -n ${az_group} -l ${az_region}  # Group Creation
az appservice plan create -n ${az_appservice_plan} -g ${az_group} --sku S1

# az webapp list-runtimes 
az webapp create -n ${az_webapp} -g ${az_group} -p ${az_appservice_plan} -r "${az_webapp_runtime}"

# Deploy web app
az webapp deployment source config-zip --src webapp.zip -g ${az-group} -n ${az-webapp}
````
