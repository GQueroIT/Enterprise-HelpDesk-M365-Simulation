Step 09 - GPO Drive Mapping

In this step, I created and applied a Group Policy Object (GPO) to automatically map the HR shared folder as a network drive for users in the HR organizational unit.

The policy was linked to the HR OU so that it would apply only to the intended users. Within the GPO, I configured a mapped drive preference to assign drive letter Z: to the shared path \\DC01\HR-Shared.

After applying the policy, I forced a Group Policy update on WORKSTATION01 and verified that the mapped drive appeared successfully as HR Shared Drive (Z:). This confirmed that the GPO was linked correctly, that the user was in the proper OU, and that both permissions and policy processing were functioning as expected.

This step demonstrates centralized administration through Group Policy and shows how user environments can be configured automatically in an enterprise domain.