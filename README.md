<div align="center">
    
 #  🇮🇱  **#BringThemHome #NeverAgainIsNow**   🇮🇱

**We demand the safe return of all citizens who have been taken hostage by the terrorist group Hamas. We will not rest until every hostage is released and returns home safely. You can help bring them back home.
https://stories.bringthemhomenow.net/**
</div>

# CVE-2023-36874 PoC

##
# 🔓 Introduction
This repository contains a proof-of-concept exploit written in C++ that demonstrates the exploitation of a vulnerability affecting the Windows Error Reporting (WER) component. The exploit showcases the steps involved in triggering the vulnerability and is intended for educational purposes only. Any malicious or unethical use of this code is strictly discouraged.
##
# The exploit follows these steps to trigger the vulnerability:

    Initialize COM by calling CoInitialize(NULL).
    Create COM interfaces to interact with WER:
        Create an instance of CLSID_ERCLuaSupport to obtain an IErcLuaSupport interface.
        Use IErcLuaSupport to create an IWerStoreFactory instance.
        Create an IWerStore instance using IWerStoreFactory.
    Start the report enumeration process by calling pIWerStore->EnumerateStart().
    Load a report using pIWerStore->LoadReport function. Replace "ReportName" with the actual report name you want to exploit.
    Submit the loaded report to trigger the vulnerability by calling pIWerReport->SubmitReport().
    Release the COM interfaces and clean up the resources:
        pIWerReport->Release()
        pIWerStore->Release()
        pIWerStoreFactory->Release()
        pIErcLuaSupport->Release()
    Uninitialize COM by calling CoUninitialize().
##
# Disclaimer

This exploit is provided for educational purposes only. It is not intended for malicious or unethical use. The repository authors and contributors are not responsible for any misuse or damage caused by the use of this code.
License
This code is released under the MIT License.
Please use this code responsibly and adhere to ethical standards when working with security vulnerabilities and exploits.
</div>
