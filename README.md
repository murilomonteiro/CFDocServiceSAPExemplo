# Getting Started

Projeto exemplo de consumo de SAP Document Services usando projeto cmis.

Testes de uso podem ser encontrados no projeto, esse projeto só demonstra o consumo dos serviço no sap CAP.
https://github.com/agea/CmisJS

## Configurar BTP

É necessário criar uma instância do document services no space do CF e gerar a chave de acesso.

cf create-service sdm free document_service

Criar a service key
cf create-service-key document_service SK_TESTE

Pega as informações da chave
cf service-key document_service SK_TESTE > SK_TESTE

Com as informações da chave, gerar um token Oauth 2.0
TokenUrl = uaa.url + '/oauth/token'
ClientID = uaa.clientid
ClientSecret = uaa.clientsecret

Depois de criado é necessário criar o repositório

POST para:

endpoints.ecmservice.url + '/rest/v2/repositories'
com o body:

{
  "repository": {
		"displayName": "Name of the repository",
		"description": "Description for the repository",
		"repositoryType": "internal",
		"isVersionEnabled":"true",
		"isVirusScanEnabled":"true",
		"skipVirusScanForLargeFile": "false",
		"hashAlgorithms":"SHA-256"
  }
}

## Learn More

Learn more at https://cap.cloud.sap/docs/get-started/.

https://github.com/agea/CmisJS

## How to Use Lib
https://github.com/agea/CmisJS/blob/master/src/cmis.spec.ts