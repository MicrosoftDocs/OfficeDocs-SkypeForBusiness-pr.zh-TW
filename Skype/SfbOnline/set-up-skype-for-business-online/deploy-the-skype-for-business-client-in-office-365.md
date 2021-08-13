---
title: 在 商務用 Skype 或 Microsoft 365 部署 Office 365
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
description: '瞭解如何在小型、商務用 Skype和大型組織中規劃及部署應用程式，並讓使用者使用。 '
ms.openlocfilehash: e503455827759966af675ff186f3d72568df613ea407f372450691511a9a6ee5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300489"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>在 商務用 Skype 或 Microsoft 365 部署 Office 365

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文說明系統管理員如何將應用程式部署商務用 Skype組織人員 **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 的選項。
  
在將 商務用 Skype部署至使用者之前，請確定您已完成設定線上版一文中的步驟 1-3 商務用 Skype[步驟](set-up-skype-for-business-online.md)。 如此一來，商務用 Skype網域進行設定，每個人都會擁有他們的授權，而您也將為貴組織的 商務用 Skype Online 設定 IM[和設定](configure-presence-in-skype-for-business-online.md)目前狀態。
  
> [!NOTE]
> 使用者若要安裝 商務用 Skype應用程式，他們必須是電腦或裝置上的本地系統管理員。 或者，他們必須是可以在電腦或裝置上安裝 App 的當地群組的一部分。 如果您的使用者不允許在裝置上安裝軟體，您必須為使用者商務用 Skype應用程式。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>適用于大多數中小型企業

 **逐步安裝指示：** 如果您有中小型企業，建議您直接要求使用者將 商務用 Skype應用程式安裝在他們的 PC 上。 指向這些[指示：安裝](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)商務用 Skype。 如果他們使用的是 Mac，請指向設定[Lync for Mac 2011 Office 365。](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) 商務用 Skype應用程式會與應用程式的其他部分分開Office安裝。
  
 **Microsoft 365 Apps 企業版客戶：** 如果您的公司使用 Office 365 方案包含 Microsoft 365 Apps 企業版 ，例如 E3 方案，則 商務用 Skype 應用程式會同時安裝，同時您的使用者下載並安裝 Word、Excel、PowerPoint 等。這也表示他們無法卸載商務用 Skype，除非他們卸載所有Office。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>選擇是否要商務用 Skype使用者使用

做[為系統管理員](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)，您可以選擇是否要讓使用者商務用 Skype應用程式。
  
- **若要控制公司中的** 每個人是否獲得軟體：Microsoft 365 系統管理中心，請前往安裝我的軟體，然後選取您想要供使用者使用的軟體。
    
    ![選擇您想要提供給公司人員的軟體。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- 若要控制公司中的特定人員是否取得軟體：請登錄 Microsoft 365 系統管理中心、前往 [使用者使用中使用者>、選取要授予軟體存取權限的人，然後按一下 [產品授權旁邊的編輯>，然後開啟或  >  關閉授權。 
    
    ![選擇您想要使用者存取的軟體。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果您需要查看指派給貴組織人員哪些方案，請Microsoft 365 系統管理中心 >****  >  **使用者 。** 從清單中選取該人員，然後查看產品 **授權下的**。 如果您使用的是傳統系統管理中心，請看下指派 **授權**。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>手動將商務用 Skype部署至您的使用者
<a name="bkmk_manual_1"> </a>

如果您希望使用者從網路商務用 Skype而不是從網際網路安裝應用程式，您可以下載安裝檔案。 To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center. 接著， **您可以選取安裝** ，然後將.exe儲存到網路位置。
  
另一個選項是下載 商務用 Skype基本應用程式。 您可以下載 Microsoft 商務用 Skype [32 (64 位基本) 。](https://www.microsoft.com/download/details.aspx?id=49440)
  
對於完整和基本 商務用 Skype 應用程式，下載設定檔案之後，您必須手動傳送 (，例如以電子郵件傳送) 網路路徑給使用者，以便他們執行安裝程式，將應用程式安裝在他們的電腦上。
  
您也可以使用這些下載，使用現有的軟體部署工具和商務用 Skype，將應用程式部署到您的使用者。
  
## <a name="for-larger-and-enterprise-organizations"></a>適用于大型企業及企業組織

> [!NOTE]
> 本節僅適用于透過商務用 Skype方案Office 365應用程式。 如果貴組織使用大量授權版本的 商務用 Skype 應用程式 ，Windows 安裝程式型 (MSI) ，請參閱在 商務用 Skype Server 中自訂 Windows[用戶端安裝](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)。
  
在許多企業或大型組織中，使用者不得在電腦上安裝軟體。 IT 部門會改為將必要的軟體部署到使用者的電腦。 IT 部門也可能想要控制其組織中所使用的網際網路或網路頻寬量，因此他們想要從網路上附近的位置安裝軟體，而不是從網際網路或整個公司網路安裝軟體。
  
有了 Office 365，如果您想要控制應用程式安裝位置，商務用 Skype數種部署應用程式的選項。 其中一些選項包括：
  
- 從 商務用 Skype 將應用程式下載到您的Microsoft 365 系統管理中心網路，如手動將 商務用 Skype[部署給使用者中所述](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)。
    
- 使用 Office **[部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)**，將 Microsoft 365 Apps 企業版或 商務用 Skype應用程式下載到您的本地網路。 然後，使用 Office部署工具將應用程式部署到您的使用者。 Office部署工具讓您能夠控制部署的某些層面，例如語言和版本 (32 位或 64 位) 。
    
- 使用現有的軟體部署工具和程式 ，例如 Microsoft Endpoint Configuration Manager，將 Microsoft 365 Apps 企業版或 商務用 Skype應用程式部署到您的使用者。 您可以使用現有的工具和程式Office[部署](https://go.microsoft.com/fwlink/p/?LinkID=626065)工具，或使用您從 Microsoft 365 系統管理中心 下載的軟體。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>使用部署工具Office詳細資訊

有關下載 Office 部署工具的詳細資訊，以及安裝 商務用 Skype 應用程式和其他 Office 365 用戶端應用程式的詳細資訊，請參閱在 Office 365[中管理軟體下載設定](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。
  
以下是使用部署工具部署應用程式Office相關步驟概觀：
  
1. **[從 Microsoft 下載Office下載](https://www.microsoft.com/download/details.aspx?id=49117)** 最新的部署工具。
    
2. 建立 configuration.xml 檔案，以與具有您想要的用戶端應用程式設定的 Office 部署工具一起使用，例如設定 (32 位或 64 位) 版本、安裝語言等。
    
3. 使用 Office 部署工具及configuration.xml檔案，將設定檔案從伺服器下載至您的Office 內容傳遞網路 (CDN) 。
    
4. 使用 Office 部署工具及configuration.xml來安裝 Office 用戶端應用程式，包括 商務用 Skype 應用程式。
    
有關使用部署Office及configuration.xml的詳細資訊，請參閱下列文章：
  
- [Office部署工具概觀](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml設定](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>有關使用Microsoft Endpoint Configuration Manager

您可以使用現有的軟體部署工具和程式 ，例如 Microsoft Endpoint Configuration Manager，來部署 商務用 Skype應用程式。 您可以使用這些工具和程式與從應用程式下載的軟體Microsoft 365 系統管理中心或Office工具。
  
若要進一步使用 Configuration Manager 部署軟體，請參閱下列文章：
  
- [在 Configuration Manager 中建立應用程式](/configmgr/apps/deploy-use/create-applications)
    
- [使用 Configuration Manager 部署應用程式](/configmgr/apps/deploy-use/deploy-applications)
    
如果您是在部署應用程式時商務用 Skype應用程式，請參閱使用 configuration Manager Microsoft 365 Apps 企業版管理Microsoft 365 Apps 企業版[應用程式](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>規劃應用程式更新商務用 Skype應用程式

在部署應用程式商務用 Skype，您必須考慮安裝更新後商務用 Skype取得更新。 這些更新可以包含新功能、安全性更新或非安全性更新，例如提供穩定性或改良效果的更新。 您需要考慮的兩個主要專案為：
  
- 您想要從何處取得更新
    
- 您想要取得功能更新的頻次
    
雖然您可以控制從何處取得更新，以及取得功能更新的頻次，但無法選擇您取得的特定安全性更新或非安全性更新。
  
 **從何處取得更新**
  
根據預設，安裝 商務用 Skype應用程式之後，當 Microsoft 提供更新時，系統會自動從網際網路下載更新。 如果您想要進一控制更新發生時間或更新的安裝位置，您可以使用 Office部署工具或群組原則來設定。
  
例如，許多組織想要先與一群使用者測試更新，然後再將更新部署到整個組織。 您可以使用部署工具Office群組原則來設定 商務用 Skype 應用程式，以從您網路上特定位置取得更新，而不是從網際網路自動取得更新。 然後，您可以使用 Office部署工具，每個月將更新下載到您的本地網路。
  
有關更新如何適用于軟體Office 365，請參閱以下文章：
  
- [更新程式概觀Microsoft 365 Apps 企業版](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [選擇如何管理更新Microsoft 365 Apps 企業版](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [設定更新Microsoft 365 Apps 企業版](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **取得功能更新的頻次**
  
除了從何處取得更新之外，您也可以控制取得用戶端新功能商務用 Skype多久。 這兩個選項如下：
  
- 如果有新功能，每個月取得功能更新
    
- 每六個月取得功能更新一次
    
對於某些組織，他們想要測試新功能的時間，因此他們只想一年取得兩次功能更新，而不是每個月。
  
您可以使用部署工具或群組原則來控制取得功能更新Office設定更新通道。 每月通道會提供每月功能更新 (大約) ，而 Semi-Annual通道則每六個月提供一次功能更新。 有關頻道的資訊，請參閱更新通道概觀[的 Microsoft 365 Apps 企業版。](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>相關主題

[設定商務用 Skype Online](set-up-skype-for-business-online.md)
  
[商務用 Skype Microsoft Teams附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
