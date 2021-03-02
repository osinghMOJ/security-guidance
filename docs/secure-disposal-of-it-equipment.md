# Secure Disposal of IT Equipment
## About this Guidance
This document is the Ministry of Justice \(MoJ\) Disposal of IT Equipment Guidance covering physical on-premise media and data as well as data residing on cloud technology. It is designed to ensure the confidentiality of MoJ data remains when physical hardware or a cloud service is decommissioned.

This information sits under the MoJs Asset Management Polices and Guidance here: https://ministryofjustice.github.io/security-guidance/#asset-management, within "Media Handling".

## Physical Media and Associated Data
The Ministry of Justice \(MoJ\) and its Executive Agencies and Arms Length Bodies use various equipment, including desktop computers, laptops, USB memory sticks, generic mobile devices, and cloud-based technology. In the case of physical equipment, it is procured and managed though MoJ suppliers, who are normally responsible for the secure disposal of the equipment when it is no longer used. Typically, a supplier managed device will have a supplier asset tag on it, making it easier to identify who to ask for help with disposal.

NCSC provides critical guidance on the secure sanitisation of storage media: https://www.ncsc.gov.uk/guidance/secure-sanitisation-storage-media, specifically the disposal and destruction of media and the data contained within it. Data sanitisation is classified as:

- **Re-use**
- **Repair**
- **Disposal** - Sanitise unwanted media and its associated data internally before it is passed outside the MoJ
- **Destruction** - Destroy the media and hence data it contains onsite or offsite.

To determine the data disposal and the media's destruction method, based on the type of equipment and its security classification, use the table below. 

If the table does not cover your exact requirement, contact the Operational Security Team: [OperationalSecurityTeam@justice.gov.uk](mailto:OperationalSecurityTeam@justice.gov.uk)

**Note:** When disposing of `SECRET` or `TOP SECRET` equipment or materials, always contact the Operational Security Team: [OperationalSecurityTeam@justice.gov.uk](mailto:OperationalSecurityTeam@justice.gov.uk)

|Equipment or asset type|Data deletion method|Disposal method|
|-----------------------|--------------------|---------------|
|Flash \(USB\)|Delete the data, or erase using manufacturer instructions.|Destroy using commercially available disintegration equipment, to produce particles of a maximum of 6 mm in any direction.|
|Hard disk drive|Overwrite the entire storage space with random or garbage data, verifying that only the data used to perform the overwrite can be read back.|Break the platters into at least four pieces. This can be done either manually or by using a commercially available destruction product suitable for hard disks. Alternatively, apply a Lower Level degauss and then apply a destructive procedure that prevents the disk from turning. For example, punch holes into the platters, or twist or bend them.|
|Magnetic tapes and floppy disks|Overwrite the entire storage space with random or garbage data, verifying that only the data used to perform the overwrite can be read back.|Destroy using a commercially available shredder that meets a recognised international destruction standard. Particles of tape should be no larger than 6 x 15 mm. Alternatively, apply a Lower Level degauss and then cut the tape to no larger than 20 mm in any direction.|
|Optical media|Data deletion is not possible. See also the note following this table.|Shred or disintegrate using equipment that meets a recognised international destruction standard. Particles should be no larger than 6 mm in any direction. A high capacity CD and DVD shredder is available at 102 Petty France, suitable for items up to `TOP SECRET`. Contact [OperationalSecurityTeam@justice.gov.uk](mailto:OperationalSecurityTeam@justice.gov.uk) for help with this option.|

**Note:** Theoretically, data deletion is possible on some RW-capable media. For simplicity, however, the safer assumption is that rewriting and therefore data deletion is not possible on optical media.

Wherever possible and appropriate, managers should pool together equipment with that of local colleagues to share service costs.

### Data Destruction Validation

As part of the physical media/data destruction by MoJ or it's suppliers, validation of its destruction needs to be carried out as data handling processes need to align to MoJs Asset Management Lifecycle policies (Responsibility for Assets, Information Classification, and Media Handling). This includes:

1. MoJ/supplier scans hard drive/physical media asset tags/barcodes
2. MoJ/supplier carries out data destruction (as per the table above)
3. MoJ/supplier confirms hard drive/physical media data destruction by providing reasonable proof; this could include;
   - Providing an inventory of physical media in their possession
   - Reconciliation carried out on the physical media scanned/received matching the physical media destroyed
   - A witness in attendance to sign a destruction certificate to be stored in a secure space/network share.

**Note**: An alternative to the above steps is to use a leading enterprise erasure tool that will provide a certificate aligned to NIST 800-88 Guidelines for Media Sanitization: https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf. Such a tool will verify:

1. When the physical media was destroyed
2. Verification was performed

Owners of the data storage devices are responsible for procuring services that meet the necessary destruction outcomes as described above. Assurance shall be required that the appropriate destruction has taken place for any locally procured MoJ assets, and that an audit trail is available for inspection upon request by MoJ security.

## Cloud Technology Data Destruction
When working on shared infrastructure (Defined as any system that pools resources in a single chassis, spreading them among independent server nodes within that same chassis to optimise performance), obtaining a decommissioning or destruction certificate needs to be approached from a different viewpoint. This cannot be carried out as per the method used for servers and disk arrays when they are wiped/blancco/destroyed/overwritten. The process used for **SECRET** items destruction and decommissioning, which used a SAN (Storage Area Network) or Virtual Machines (VMs), is stepped through below and shown in the diagram above. 

1. Install a screen recording piece of software on the operators terminal
2. Ideally, have a witness sit next to the operator and start the screen recording software (if not possible, then the witness can view the video afterwards)
3. Encryption keys for the solution should be archived for backup retention purposes, if necessary, onto a secure storage space
4. For each of the following technology, the operator should run an initial listing (ideally cut and paste into a text document), run the task, then perform another listing to show that the change has occurred.
   - Depending on Backups on a SAN/Site basis, some jobs may need to be removed. You should not delete the backups, however, without consulting the retention policy      (This also applies to steps below).
   - The operator, if possible, formats the SAN areas used for the files and zero’s them, then deletes the various LUNs, Arrays, Volumes etc., for the SAN and            reallocates them to free space. This is then verified with listings of the SAN.
   - VMs are permanently deleted in the VMWare (or equivalent control panel), and attempts to list and restart the machine are made to show it has been permanently      removed
   - Any FW (Forwarder) or other SEF (Search Engine Friendly) config should be removed.
   - Any switch config (containing IP addresses and subnet masks) should be removed.
   - Screen recording software is stopped.
   - Witness signs the decommissioning certificate, and the video is stored in secure storage space.


**Note**: There are free versions of screen recorders that need to be assessed for use, including;
- Confirming it is not Russian, Chinese or any other countries spyware software
- AV scanning passed before use 
- The software does not default to loading the video recording to the Internet.


If you have any concerns about moving items between sites securely, contact the Operational Security Team: [OperationalSecurityTeam@justice.gov.uk](mailto:OperationalSecurityTeam@justice.gov.uk)

## Contacts

The following organisations are approved to help you with security disposal of equipment:

-   TYR security: [g-cloud@tyr-security.co.uk](mailto:g-cloud@tyr-security.co.uk)
-   Data eliminate: [info@dataeliminate.com](mailto:info@dataeliminate.com)

## Contact details

For any further questions relating to security, contact: [security@justice.gov.uk](mailto:security@justice.gov.uk), or for security advice, contact the Cyber Assistance Team [CyberConsultancy@digital.justice.gov.uk](mailto:CyberConsultancy@digital.justice.gov.uk).

## Feedback

> If you have any questions or comments about this guidance, such as suggestions for improvements, please contact: [itpolicycontent@digital.justice.gov.uk](mailto:itpolicycontent@digital.justice.gov.uk).

