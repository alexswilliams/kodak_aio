# Offline Installers for Kodak Windows AIO Drivers

The Kodak AIO installer (aio_install.exe) is an online installer which downloads remote msi and cab files from kodak's download endpoint.

The installer, however, reaches out over unsecured HTTP, and is redirected to an HTTPS endpoint, which no longer supports TLSv1.0 (the only version the installer seems capable of negotiating.)

The HTTP endpoint (as discovered with wireshark) is as follows:
 - http://download.kodak.com/digital/software/inkjet/v1_0/v3_2//summary.xml?src=WDL&ver=7.09

Eventually this leads to a list of MSI and CAB files to be installed here:
 - https://download.kodak.com/digital/software/inkjet/v7_9/Manifest_IFW.xml

As Kodak appears to have exited the inkjet business, these files are saved here to prevent AIO devices becoming obsoleted.

## Potentially Supported Models

The manifest file appears to be the same for all the models in this list.  Please raise issue if any of the following don't work.

 - Hero 2.2
 - Hero 4.2
 - ESP 1.2
 - ESP 3.2
 - Hero 3.1
 - Hero 5.1
 - Hero 7.1
 - Hero 9.1
 - Office Hero 6.1
 - ESP Office 2100 Series
 - ESP C100 Series
 - ESP C300 Series
 - ESP 3200 Series
 - ESP 5200 Series
 - ESP 7200 Series
 - ESP 9200 Series
 - ESP Office 6100 Series
 - ESP 3
 - ESP 5
 - ESP 7
 - ESP 9
 - 5100
 - 5300
 - 5500


## Installation Instructions

There are different MSIs for x86 and x64 architectures - if in doubt, a good approach is to try x64 first and x86 if this fails.

 - Download or clone this repository

 - Run prereq/PreReq.msi
 - Run msxml6/msxml6_x64.msi (or ..._x86.msi)
 - Run essentials/essentials.msi
 - Run printer/aioprntx64.msi (or ...x86.msi)
 - Run printer2/aioprntx64.msi (or ...x86.msi)
 - Run scanner/aioscnnr.msi
 - Run scanner2/aioscnnr.msi

If you want the control center as well:
 - Run center/center.msi

If you want to OCR software too:
 - Run ocr/ocr.msi

