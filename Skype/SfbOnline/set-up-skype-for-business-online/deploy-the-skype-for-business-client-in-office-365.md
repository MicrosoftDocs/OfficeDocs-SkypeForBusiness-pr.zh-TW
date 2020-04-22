---
title: 在 Microsoft 365 aor Office 365 中部署商務用 Skype 用戶端
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
description: '瞭解如何在小型、中型及大型組織中規劃及部署商務用 Skype，並讓您的使用者使用。 '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777238"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中部署商務用 Skype 用戶端

本文說明您的系統**[管理員](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 可以如何將商務用 Skype 應用程式部署到貴組織中的人員的選項。
  
在您將商務用 Skype 部署到您的使用者之前，請先確認已完成[設定商務用 Skype Online 一](set-up-skype-for-business-online.md)文中的步驟1-3。 如此一來，您的網域就會設定商務用 Skype，所有人都會擁有其授權，而且您將[在商務用 Skype Online 中](configure-presence-in-skype-for-business-online.md)設定 IM 並設定目前狀態。
  
> [!NOTE]
> 針對安裝商務用 Skype 應用程式的使用者，他們必須是電腦或裝置上的本機系統管理員。 或者，必須是本機群組的一部分，才能在他們的電腦或裝置上安裝應用程式。 如果您的使用者不能在裝置上安裝軟體，您必須安裝商務用 Skype 應用程式。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>對於大部分的中小型企業

 **逐步安裝指示：** 如果您有小型或中型企業版，我們建議您只要求您的使用者在電腦上安裝商務用 Skype 應用程式。 請將其指向以下指示：[安裝商務用 Skype](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)。 如果他們使用 Mac，請將其指向[針對 Office 365 設定 Lync For Mac 2011](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)。 商務用 Skype app 是獨立于其他 Office 應用程式安裝的。
  
 **適用于企業客戶的 Microsoft 365 應用程式：** 如果您的企業使用的是包含適用于企業的 Microsoft 365 應用程式的 Office 365 方案（例如 E3 方案），則在您的使用者下載及安裝 Word、Excel、PowerPoint 等時，就會安裝商務用 Skype 應用程式。這也表示他們無法卸載商務用 Skype，除非他們已卸載所有的 Office。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>選擇是否要讓您的使用者使用商務用 Skype

如果您是系統[管理員](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)，您可以選擇是否要讓您的使用者使用商務用 Skype 應用程式。
  
- **若要控制貴公司中的每個人是否都能取得軟體**：登入 Microsoft 365 系統管理中心，移至 [**安裝我的軟體**]，然後選取您要提供給使用者的軟體。
    
    ![選擇您要提供給公司中人員的軟體。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **若要控制貴公司中的特定人員是否取得軟體**：登入 Microsoft 365 系統管理中心，移至 [**使用者** > 作用中的**使用者**]，選取您要授與本軟體存取權的人員，然後按一下 [**產品授權**] 旁的 [**編輯**]，然後開啟或關閉授權。
    
    ![選擇您想要讓使用者存取哪一個軟體。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果您需要查看已將哪些方案指派給貴組織中的人員，請登入 Microsoft 365 系統管理中心 >**使用者** > 作用中的**使用者**。 從清單中選取該人員，然後查看 [**產品授權**]。 如果您使用的是傳統系統管理中心，請在 [**已指派授權**] 下查看。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>手動將商務用 Skype 部署給您的使用者
<a name="bkmk_manual_1"> </a>

如果您想讓使用者從網路上的某個位置（而不是從網際網路）安裝商務用 Skype 應用程式，您可以下載安裝檔案。 若要這樣做，請移至 Microsoft 365 系統管理中心的 [**手動部署使用者軟體**] 區段。 接著，您可以選取 [**安裝**] 並將 setup.exe 檔案儲存到網路位置。
  
另一個選項是下載適用于您使用者的商務用 Skype 基本應用程式。 您可以下載[Microsoft 商務用 Skype 基本版（32或64位版）](https://www.microsoft.com/download/details.aspx?id=49440)。
  
針對完整與基本的商務用 Skype 應用程式，您必須手動傳送（例如，在電子郵件中）使用者的網路路徑，讓他們可以執行安裝程式，以在電腦上安裝應用程式。
  
您也可以使用這些下載，透過現有的軟體部署工具和程式，將商務用 Skype 應用程式部署到您的使用者。
  
## <a name="for-larger-and-enterprise-organizations"></a>針對大型企業組織

> [!NOTE]
> 本節僅適用于透過 Office 365 方案提供的商務用 Skype app。 如果您的組織使用的是 Windows 安裝程式（MSI）版商務用 Skype 應用程式的大量授權版本，請參閱[在商務用 Skype Server 中自訂 Windows 用戶端安裝](https://technet.microsoft.com/library/jj204934.aspx)。
  
在許多企業或大型組織中，不允許使用者在電腦上安裝軟體。 相反地，IT 部門會將必要的軟體部署到使用者的電腦上。 IT 部門也可能想要控制組織中所使用的網際網路或網路頻寬量，所以他們想要從網路上的鄰近位置，而不是透過網際網路或整個公司網路來安裝軟體。
  
有了 Office 365，如果您想要控制其安裝位置，您有幾個選項可供您部署商務用 Skype app。 其中一些選項包括下列各項：
  
- 如[手動將商務用 skype 部署給使用者](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)，請從 Microsoft 365 系統管理中心將商務用 skype 應用程式下載到您的本機網路。
    
- 使用**[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)**，將適用于企業的 Microsoft 365 App 或商務用 Skype 應用程式下載到您的本機網路。 然後，使用 Office 部署工具，將應用程式部署到您的使用者。 Office 部署工具可讓您控制部署的特定方面，例如語言與版本（32位或64位）。
    
- 使用您現有的軟體部署工具和程式（例如 Microsoft 端點建構管理員），將適用于企業的 Microsoft 365 app 或商務用 Skype 應用程式部署到您的使用者。 您可以在[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)或從 Microsoft 365 系統管理中心下載的軟體中使用現有的工具和程式。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>有關使用 Office 部署工具的詳細資訊

如需下載 Office 部署工具的詳細資訊，以及安裝商務用 Skype 應用程式及其他 Office 365 用戶端應用程式的詳細資訊，請參閱[管理 Office 365 中的軟體下載設定](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。
  
以下是使用 Office 部署工具部署 app 所涉及的步驟：
  
1. 從 Microsoft 下載中心**[下載最新的 Office 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)**。
    
2. 建立要與 Office 部署工具搭配使用的 config.xml 檔案，該工具具有您想要的用戶端應用程式設定，例如設定版本（32位或64位）、安裝語言等。
    
3. 使用 Office 部署工具和 config.xml 檔案，將安裝檔案從 Office 內容傳遞網路（CDN）下載到您的本機或內部網路。
    
4. 使用 Office 部署工具和 .xml 來安裝 Office 用戶端應用程式，包括商務用 Skype 應用程式。
    
如需使用 Office 部署工具和 config.xml 檔案的詳細資料，請參閱下列文章：
  
- [Office 部署工具概述](https://technet.microsoft.com/library/jj219422.aspx)
    
- [配置 .xml 設定](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>有關使用 Microsoft 端點 Configuration Manager 的詳細資訊

您可以使用現有的軟體部署工具和程式（例如 Microsoft 端點建構管理員）來部署商務用 Skype 應用程式。 您可以將這些工具與程式與您從 Microsoft 365 系統管理中心或 Office 部署工具下載的軟體搭配使用。
  
如需使用 Configuration Manager 部署軟體的詳細資訊，請參閱下列文章：
  
- [在 Configuration Manager 中建立應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [使用 Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
如果您要部署適用于企業的 Microsoft 365 應用程式的商務用 Skype app，請參閱[使用 Configuration Manager 管理企業版 microsoft 365 應用](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)程式。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>規劃商務用 Skype 應用程式的更新

在部署商務用 Skype app 的過程中，您必須考慮在安裝商務用 Skype 之後，您想要如何取得更新。 這些更新可能包含新功能、安全性更新或非安全性更新，例如提供穩定性或效能改善的更新。 您需要考慮的兩個主要事項是：
  
- 您要從何處取得更新
    
- 您想要多久取得一項功能更新
    
雖然您可以控制從何處取得更新，以及您取得功能更新的頻率，但您無法選擇您要取得的特定安全更新或非安全性更新。
  
 **從何處取得更新**
  
根據預設，在安裝商務用 Skype 應用程式之後，系統會在 Microsoft 提供更新時自動從網際網路下載更新。 如果您想要進一步控制更新發生的時間或更新的安裝位置，您可以使用 Office 部署工具或群組原則來設定。
  
例如，許多組織想要在整個組織中部署更新之前，先與一組使用者進行測試。 您可以使用 Office 部署工具或群組原則來設定商務用 Skype 應用程式，以從網路上的特定位置取得更新，而不是從網際網路自動取得更新。 接著，您可以使用 Office 部署工具，將每個月的更新下載到您的本機網路。
  
如需有關 Office 365 軟體更新運作方式的詳細資訊，請參閱下列文章：
  
- [適用于企業版 Microsoft 365 應用程式的更新程式概覽](https://technet.microsoft.com/library/dn761709.aspx)
    
- [選擇管理 windows 版 Microsoft 365 應用程式的更新方式](https://technet.microsoft.com/library/dn761707.aspx)
    
- [為適用于企業的 Microsoft 365 應用程式設定更新設定](https://technet.microsoft.com/library/dn761708.aspx)
    
  **取得功能更新的頻率**
  
除了您從中取得更新的位置之外，您也可以控制您為商務用 Skype 用戶端取得新功能的頻率。 這兩個選項如下所示：
  
- 如果有新功能，請在每個月取得功能更新
    
- 取得功能每六個月更新一次
    
針對某些組織，他們想要時間來測試新功能，因此他們想要每年只取得兩次的功能更新，而不是每個月。
  
您可以透過使用 Office 部署工具或群組原則來設定更新通道，以控制您取得功能更新的頻率。 每月頻道可讓您每月（約）的功能更新，而半年通道提供每六個月的功能更新。 如需有關通道的詳細資訊，請參閱適用[于企業的 Microsoft 365 應用程式更新通道的概覽](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。
  
## <a name="related-topics"></a>相關主題

[設定商務用 Skype Online](set-up-skype-for-business-online.md)
  
[商務用 Skype 和 Microsoft 團隊附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
