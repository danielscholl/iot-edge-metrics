FROM mcr.microsoft.com/windows/servercore:ltsc2019 AS builder

WORKDIR "c:\\program files\\influxdb"

RUN powershell.exe -Command \
  $ErrorActionPreference = 'Stop'; \
  Invoke-WebRequest https://dl.influxdata.com/influxdb/releases/influxdb-1.7.7_windows_amd64.zip -OutFile c:\influxdb.zip ; \
  Expand-Archive 'c:/influxdb.zip' 'C:/' ; \
  Copy-Item -Path c:\influxdb-1.7.7-1\* . ; \
  Remove-Item c:\influxdb.zip -Force ; \
  Remove-Item -Path c:\influxdb-1.7.7-1 -Force -Recurse

COPY influxdb.conf .

EXPOSE 8086
CMD ["influxd.exe", "-config", "influxdb.conf"]