# More information about the aspnet base container;
# https://hub.docker.com/r/microsoft/aspnet/
FROM microsoft/aspnet

# Create the website directory which hold the sitecore website files.
RUN mkdir C:\website

# DNS Resolver Cache Service
RUN set-itemproperty -path 'HKLM:\SYSTEM\CurrentControlSet\Services\Dnscache\Parameters' \
    -Name ServerPriorityTimeLimit -Value 0 -Type DWord

# Configure IIS
RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    New-IISSite -Name "Sitecore" -PhysicalPath C:\website -BindingInformation "*:8000:"

# Make the exposed port is the same as the -BindingInformation option
# given in the powershell command.
EXPOSE 8000