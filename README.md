- RUN AS ADMIN 
Purpose:
This script collects and exports various system security and firmware information, specifically focusing on certificates and UEFI firmware details as well as All EFI activity.

Certificate Data Collection:  
Exports certificates from several Windows certificate stores (My, Root, TrustedPeople) into CSV files for easy review.
Searches for EFI-related certificates (subjects containing "EFI", "SecureBoot", or "Microsoft") and exports those as well.

This application primarily relies on system commands and certificate stores to gather EFI-related information and certificates, 
including EFI boot entries and Secure Boot status, rather than directly scanning the System/EFI directory for .efi files.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Main Concept of the EFI Cert Output and Understanding it  
Subject:
Describes the entity or organization associated with the certificate. Legitimate EFI certificates typically have specific, trusted subjects issued by recognized authorities, such as Microsoft or hardware vendors.

Thumbprint:
A unique cryptographic hash (usually SHA-1 or SHA-256) representing the certificate. Known, trusted certificates have predefined thumbprints.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

You will Use the Subject to read the Certificate as most will be listed by trusted Hardware vendors like microsoft etc.

The script retrieves UEFI firmware boot entries using the command bcdedit /enum firmware. 
These entries describe the various boot options and configurations stored in the system firmware, which are critical in understanding the boot process.

You will want to scan this for unwanted entrys or unkown vendors 
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

