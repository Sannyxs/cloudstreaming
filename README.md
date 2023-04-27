# ATENÇÃO!
Essa script é apenas uma modificação nela para melhorias.

# Cloud NVIDIA Sunshine

## What is it?
Uma solução de um clique do Powershell para habilitar o NVIDIA GeForce Experience GameStream em uma máquina em nuvem com uma GPU compatível com GRID. Houve um [tópico discutindo isso no fórum xda-developers](https://forum.xda-developers.com/showthread.php?t=2394478), mas todo o processo não ficou claro em quais versões dos drivers GRID e GeForce Experience para usar e exigia algumas instalações tediosas e soluções alternativas, já que o GeForce Experience que o suportava era atualizado automaticamente para o mais novo. Este script resolverá todos os problemas com um único script.
&nbsp;  
&nbsp;  

## Instalação
Copie e cole esses comandos no prompt do powershell da máquina:
```
[Net.ServicePointManager]::SecurityProtocol = "tls12, tls11, tls";Set-ExecutionPolicy Unrestricted;Invoke-WebRequest -Uri https://github.com/acceleration3/cloudgamestream/releases/download/resolution-fix/cloudgamestream.zip -OutFile arch.zip;Add-Type -Assembly "System.IO.Compression.Filesystem";$dir = [string](Get-Location);rmdir -r cloudgamestream-master -ErrorAction Ignore;[System.IO.Compression.ZipFile]::ExtractToDirectory($dir + "\arch.zip", $dir);cd cloudgamestream;./Setup.ps1
```
Ou você pode baixar o script original e os binários de [here](https://github.com/acceleration3/cloudgamestream/releases/download/resolution-fix/cloudgamestream.zip).  
&nbsp;  
&nbsp;  

## Compatibilidade
Tested and working on the following:

* OS:
	* Windows 10 Pro ( Only Drivers 472.39 Azure/ Only Driver 461.39 GCP/ AWS Funciona nos mais atuais do bucket!
	* Windows Server 2019
	* Windows Server 2016
	
* Platforms:
	* Azure Tesla M60/Tesla T4
	* Amazon AWS EC2 G4DN Tesla T4
	* Google Cloud Platform Tesla T4
	* Google Cloud Platform Tesla P4
	
&nbsp;  
**WARNING: As máquinas fornecidas pela Bright/Space supostamente têm compatibilidade com o Sunshine e podem bloquear sua VM.**  
&nbsp;  
&nbsp;  
&nbsp;  
## FAQ
### Isso funcionará em \<insira a plataforma e o nome da instância aqui\>?
