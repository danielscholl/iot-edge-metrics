FROM mcr.microsoft.com/windows/servercore:ltsc2019

WORKDIR "c:\\program files\\grafana"

RUN powershell.exe -Command \
  $ErrorActionPreference = 'Stop'; \
  Invoke-WebRequest https://dl.grafana.com/oss/release/grafana-6.3.3.windows-amd64.zip -OutFile c:\grafana.zip ; \
  Expand-Archive 'c:/grafana.zip' 'C:/' ; \
  Copy-Item -Path c:\grafana-6.3.3\* . -Recurse ; \
  Remove-Item c:\grafana.zip -Force ; \
  Remove-Item -Path c:\grafana-6.3.3 -Force -Recurse

COPY custom.ini conf

COPY provisioning "conf\provisioning"

WORKDIR "c:\\program files\\grafana\\bin"

EXPOSE 8080
CMD ["grafana-server.exe"]