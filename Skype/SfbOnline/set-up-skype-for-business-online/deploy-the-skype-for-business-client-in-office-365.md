---
title: 在 Microsoft 365 或 Office 365 部署商務用 Skype 用戶端
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '瞭解如何在小型、中型和大型組織中規劃及部署商務用 Skype，以及讓使用者使用 Skype。 '
ms.openlocfilehash: 7a2ba51a315b77c501735be863f342c1bdb1548f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097289"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中部署商務用 Skype 用戶端

本文說明系統管理員如何將商務用 Skype **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 應用程式部署給貴組織的人員的選項。
  
在將商務用 Skype 部署給使用者之前，請確定您已完成設定商務用 [Skype Online](set-up-skype-for-business-online.md)一文的步驟 1-3。 如此一來，商務用 Skype 就會與網域一起設定，每個人都會擁有他們的授權，而您將為貴組織的 [商務](configure-presence-in-skype-for-business-online.md) 用 Skype Online 設定 IM 和設定目前狀態。
  
> [!NOTE]
> 使用者若要安裝商務用 Skype 應用程式，他們必須是電腦或裝置上的當地系統管理員。 或者，他們必須是可以在電腦或裝置上安裝 App 的當地群組的一部分。 如果您的使用者不允許在裝置上安裝軟體，您必須為使用者安裝商務用 Skype 應用程式。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>適用于大多數中小型企業

 **逐步安裝指示：** 如果您有中小型企業，建議您直接要求使用者在您的電腦上安裝商務用 Skype 應用程式。 指向這些指示：[安裝商務用 Skype。](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) 如果他們使用的是 Mac，請指向設定 [Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)。 商務用 Skype 應用程式會與 Office App 的其餘部分分開安裝。
  
 **適用于企業客戶的 Microsoft 365 應用程式：** 如果您的公司使用的是包含 Microsoft 365 企業版 App 的 Office 365 方案 ，例如 E3 方案，則使用者下載並安裝 Word、Excel、PowerPoint 等商務用 Skype App 時，即會同時安裝。這也表示他們無法卸載商務用 Skype，除非他們卸載所有 Office。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>選擇是否要讓使用者使用商務用 Skype

做 [為系統管理員](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) ，您可以選擇是否要讓使用者使用商務用 Skype 應用程式。
  
- **若要控制公司中的** 每個人是否獲得軟體：請登錄 Microsoft 365 系統管理中心，前往安裝我的軟體，然後選取您想要供使用者使用的軟體。
    
    ![選擇您想要提供給公司人員的軟體。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- 若要控制公司中的特定人員是否取得軟體：請登錄 Microsoft 365 系統管理中心、前往[使用者使用中使用者>、選取要授予軟體存取權限的人，然後按一下 [產品授權旁的編輯>，然後開啟或關閉授權。  >    
    
    ![選擇您想要使用者存取的軟體。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果您需要查看組織中已指派哪些方案給人員，請以使用者活動使用者> **Microsoft** 365 系統  >  **管理中心**。 從清單中選取人員，然後查看產品 **授權下的**。 如果您使用的是傳統系統管理中心，請看下指派 **授權**。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>手動將商務用 Skype 部署給使用者
<a name="bkmk_manual_1"> </a>

如果您希望使用者從您網路上的位置安裝商務用 Skype 應用程式，而不是從網際網路安裝，您可以下載安裝檔案。 若要這麼做，請前往Microsoft 365 系統管理中心的手動部署使用者軟體區段。 接著，您可以選取安裝 **，** 然後將安裝程式 .exe 檔案儲存到網路位置。
  
另一個選項是下載適用于使用者的商務用 Skype Basic 應用程式。 您可以下載[Microsoft 商務用 Skype Basic (32 或 64 位) 。](https://www.microsoft.com/download/details.aspx?id=49440)
  
針對完整及基本商務用 Skype 應用程式，下載設定檔案之後，您必須手動傳送 (，例如以電子郵件傳送) 網路路徑給使用者，以便使用者執行安裝程式，將應用程式安裝在他們的電腦上。
  
您也可以使用這些下載，使用現有的軟體部署工具和程式，將商務用 Skype 應用程式部署給使用者。
  
## <a name="for-larger-and-enterprise-organizations"></a>適用于大型企業及企業組織

> [!NOTE]
> 本節僅適用于透過 Office 365 方案提供的商務用 Skype 應用程式。 如果貴組織使用大量授權版的商務用 Skype 應用程式 ，即 Windows Installer 型 (MSI) ，請參閱在商務用 Skype Server 中自訂 Windows 用戶端 [安裝](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)。
  
在許多企業或大型組織中，使用者不得在電腦上安裝軟體。 IT 部門會改為將必要的軟體部署到使用者的電腦。 IT 部門也可能想要控制其組織中所使用的網際網路或網路頻寬量，因此他們想要從網路上附近的位置安裝軟體，而不是從網際網路或整個公司網路安裝軟體。
  
有了 Office 365，如果您想要控制安裝位置，您有幾個選項可以部署商務用 Skype 應用程式。 其中一些選項包括下列專案：
  
- 從 Microsoft 365 系統管理中心將商務用 Skype 應用程式下載到您的當地網路，如手動將商務用 [Skype 部署給使用者中所述](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)。
    
- 使用 **[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 將 Microsoft 365 企業版 App 或商務用 Skype 應用程式下載至您的當地網路。 然後，使用 Office 部署工具將應用程式部署到您的使用者。 Office 部署工具讓您能夠控制部署的某些層面，例如語言和版本 (32 位或 64 位) 。
    
- 使用現有的軟體部署工具和程式 ，例如 Microsoft 端點組組管理員，將 Microsoft 365 企業版 App 或商務用 Skype 應用程式部署給使用者。 您可以在 Office 部署工具或從 Microsoft [](https://go.microsoft.com/fwlink/p/?LinkID=626065) 365 系統管理中心下載的軟體中使用您的現有工具和程式。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>有關使用 Office 部署工具之詳細資訊

有關下載 Office 部署工具的詳細資訊，以及安裝商務用 Skype 應用程式和其他 Office 365 用戶端應用程式的詳細資訊，請參閱在 [Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)中管理軟體下載設定 。
  
以下是使用 Office 部署工具部署應用程式所涉及步驟概觀：
  
1. **[從 Microsoft 下載中心下載](https://www.microsoft.com/download/details.aspx?id=49117)** 最新的 Office 部署工具。
    
2. 建立 configuration.xml 檔案，以用於具有您想要的用戶端應用程式設定之 Office 部署工具，例如設定版本 (32 位或 64 位) 、安裝語言等。
    
3. 使用 Office 部署工具和 configuration.xml檔案，從 Office 內容傳遞網路或 CDN (下載設定檔案至您的) 。
    
4. 使用 Office 部署工具configuration.xml Office 用戶端應用程式 ，包括商務用 Skype 應用程式。
    
有關使用 Office 部署工具及configuration.xml的詳細資訊，請參閱下列文章：
  
- [Office 部署工具概觀](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml設定](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>有關使用 Microsoft 端點組組管理員的更多資訊

您可以使用現有的軟體部署工具和程式 ，例如 Microsoft 端點組組管理員，來部署商務用 Skype 應用程式。 您可以在從 Microsoft 365 系統管理中心下載的軟體或 Office 部署工具中，使用這些工具和程式。
  
若要進一步使用 Configuration Manager 部署軟體，請參閱下列文章：
  
- [在 Configuration Manager 中建立應用程式](/configmgr/apps/deploy-use/create-applications)
    
- [使用 Configuration Manager 部署應用程式](/configmgr/apps/deploy-use/deploy-applications)
    
如果您要部署商務用 Skype 應用程式，做為部署企業用 Microsoft 365 App 的一部分，請參閱使用 Configuration Manager 管理企業版 [Microsoft 365 應用程式](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>規劃商務用 Skype 應用程式的更新

在部署商務用 Skype App 時，您必須考慮安裝商務用 Skype 之後，如何取得更新。 這些更新可以包含新功能、安全性更新或非安全性更新，例如提供穩定性或改良效果的更新。 您需要考慮的兩個主要專案為：
  
- 您想要從何處取得更新
    
- 您想要取得功能更新的頻次
    
雖然您可以控制從何處取得更新，以及取得功能更新的頻次，但無法選擇您取得的特定安全性更新或非安全性更新。
  
 **從何處取得更新**
  
根據預設，安裝商務用 Skype App 之後，當 Microsoft 提供更新時，系統會自動從網際網路下載更新。 如果您想要進一控制更新發生的時間，或更新的安裝位置，您可以使用 Office 部署工具或群組原則來設定。
  
例如，許多組織想要先與一群使用者測試更新，然後再將更新部署到整個組織。 您可以使用 Office 部署工具或群組原則來設定商務用 Skype 應用程式，以從您網路上特定位置取得更新，而不是從網際網路自動取得更新，以執行這項操作。 然後，您可以使用 Office 部署工具每個月將更新下載到您的本地網路。
  
有關更新如何適用于 Office 365 軟體之詳細資訊，請參閱以下文章：
  
- [適用于企業的 Microsoft 365 應用程式更新程式概觀](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [選擇如何管理適用于企業的 Microsoft 365 應用程式更新](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [設定適用于企業的 Microsoft 365 應用程式更新設定](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **取得功能更新的頻次**
  
除了從何處取得更新之外，您也可以控制取得商務用 Skype 用戶端新功能的機次。 這兩個選項如下：
  
- 如果有新功能，每個月取得功能更新
    
- 每六個月取得功能更新一次
    
對於部分組織，他們想要測試新功能的時間，因此他們只想一年取得兩次功能更新，而不是每個月。
  
您可以使用 Office 部署工具或群組原則來設定更新通道，控制取得功能更新的頻次。 每月通道會提供每月功能更新 (大約) ，而 Semi-Annual通道則每六個月提供一次功能更新。 有關頻道的資訊，請參閱企業版 [Microsoft 365 應用程式更新通道概觀](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。
  
## <a name="related-topics"></a>相關主題

[設定商務用 Skype Online](set-up-skype-for-business-online.md)
  
[商務用 Skype 和 Microsoft Teams 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
