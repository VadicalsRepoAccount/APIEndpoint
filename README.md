# EndpointAPI

EndpointAPI is a specialized backend service designed to support the Dependency Installer. It acts as a centralized data repository, providing the installer with real-time metadata, download sources, and configuration fixes for critical software dependencies.

---

## Core Functionality

* **Dependency Management**: Serves versioning data for environments including Node.js, VC++ Redistributables, and .NET Frameworks.
* **Dynamic Fixes**: Hosts a dedicated endpoint for hotfixes, allowing the installer to adapt to installation errors or environment changes without requiring a client-side update.
* **Centralized Metadata**: Stores checksums and silent install flags to ensure consistent installation across different target machines.

---

## API Reference

### Get Dependency Data
`GET /api/dependencies`
* Returns a list of all available software packages and their installation parameters.

### Get Fixes and Patches
`GET /api/fixes`
* Returns logic for handling common installation hurdles.

**Example Response:**
```json
{
  "fix_id": "vc_redist_2015_conflict",
  "target": "VC++ Redistributable 2015",
  "issue": "Existing version prevents clean install",
  "action": "REPAIR",
  "flags": "/repair /quiet /norestart",
  "timestamp": "2023-10-27T14:30:00Z"
}
```
