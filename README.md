# pp-remove-bloat
Windows 10 Provisioning Package that removes bloat UWP packages.
The packages are removed from currently logged in user and from provisioned packages, which prevents them from installing to new accounts.

:exclamation: This might not uninstall packages from other existing accounts.

## Installation
Double click the ``.ppkg`` file to install, or use PowerShell ``Install-ProvisioningPackage package.ppkg -QuietInstall``.

## Adding packages for uninstallation
You need the package name and publisher Id to add it to the provisioning package. You can get all necessary information with this PowerShell command ``Get-AppXPackage | Select Name,PublisherId``. Use the following format for package name for the rest of the steps``<Name>_<PublisherId>``.

After that use Windows Configuration Designer to edit the provisioning package and add the package under ``Runtime settings/UniversalAppUninstall/RemoveProvisionedApp`` and ``Runtime settings/UniversalAppUninstall/Uninstall`` and choose the action ``RemoveProvisionedApp`` or ``Uninstall`` for each package, then just build the provisioning package.

## UWP packages removed by this provisioning package
* Microsoft.BingWeather_8wekyb3d8bbwe
* Microsoft.GetHelp_8wekyb3d8bbwe
* Microsoft.Getstarted_8wekyb3d8bbwe
* Microsoft.Messaging_8wekyb3d8bbwe
* Microsoft.Microsoft3DViewer_8wekyb3d8bbwe
* Microsoft.MicrosoftOfficeHub_8wekyb3d8bbwe
* Microsoft.MicrosoftSolitaireCollection_8wekyb3d8bbwe
* Microsoft.MixedReality.Portal_8wekyb3d8bbwe
* Microsoft.MSPaint_8wekyb3d8bbwe
* Microsoft.Office.OneNote_8wekyb3d8bbwe
* Microsoft.OneConnect_8wekyb3d8bbwe
* Microsoft.Print3D_8wekyb3d8bbwe
* Microsoft.SkypeApp_kzf8qxf38zg5c
* Microsoft.Wallet_8wekyb3d8bbwe
* Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe
* Microsoft.XboxApp_8wekyb3d8bbwe
* Microsoft.YourPhone_8wekyb3d8bbwe
* Microsoft.WindowsMaps_8wekyb3d8bbwe
* Microsoft.People_8wekyb3d8bbwe
* Microsoft.549981C3F5F10_8wekyb3d8bbwe *(Cortana)*
