# send2geoadmin

Send your local geodata to the [Swiss federal geoportal][geoadmin].

## Goal

This is a proof-of-concept web application which takes your local
geodata files and shows it in
[the geoportal of the Swiss federal government][geoadmin]. It is far
from complete and should only make one point: You don't need a desktop
GIS to view your geodata on your harddrive (SSD).

The implementation is based on [Azure][]. 

## Demo

A running version is live at
<http://send2geoadmin.azurewebsites.net>. Please use responsibly.

## Supported file formats

Currently:

- KMZ
- GeoJSON

## Installation and Deployment

This application is running on an Azure website. Here are some rough
steps to recreate it on your own:

- Go to your management portal at <https://manage.windowsazure.com/>
  and create a new website (or use the Node.js command line tools) and
  possibly a blob storage.
- Define an app setting called `storage_access_key` for the
  BlobStorage where you want to temporarily store the uploaded files,
  see also
  [this blog post on application strings][azure-connection-strings].
- Copy the code into your repository.
- Put the Python SDK for Azure in the directory,
  <https://github.com/WindowsAzure/azure-sdk-for-python>
- Push the code to [Azure][].

## Todo

- More geodata file formats. For example, one could easily integrate
  some [FME][] services.
- Take care of projections. Currently, we hope your local files are in
  WGS84.
- Adopt to other cloud services.

## Credits

The drag'n'drop code is adapted from
<http://html5demos.com/dnd-upload>. The conversion to KML is done on a
separate Node.JS instance using <https://github.com/mapbox/tokml>.

## Author

Stephan Heuel, stephan.heuel@ebp.ch

[FME]: http://www.safe.com/fme/fme-technology/
[Azure]: http://windowsazure.com
[geoadmin]: http://map.geo.admin.ch
[azure-connection-strings]: http://blogs.msdn.com/b/windowsazure/archive/2013/07/17/windows-azure-web-sites-how-application-strings-and-connection-strings-work.aspx
