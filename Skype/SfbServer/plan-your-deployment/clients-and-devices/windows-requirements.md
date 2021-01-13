---
title: Windows 用戶端需求和軟體支援
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
description: 摘要：在規劃商務用 Skype Server 時，複查 Windows 用戶端支援需求。
ms.openlocfilehash: 105c4ec8824b2b6f5f7a68349659ca10bb82c737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816063"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 用戶端需求和軟體支援
 
**摘要：** 在規劃商務用 Skype Server 時，請複查 Windows 用戶端支援需求。
  
本節摘要支援商務用 Skype Windows 用戶端所需的軟體。 當 Microsoft 365 或 Office 365 安裝時，即會安裝這些用戶端，也可以在 [所有裝置上下載商務用 Skype](https://products.office.com/skype-for-business/download-app?tab=tabs-3)。
  
> [!NOTE]
> 商務用 Skype 的線上會議增益集（支援來自 Outlook 郵件和共同作業用戶端的會議管理）會自動隨商務用 Skype 安裝。 
  
**商務用 Skype 用戶端和線上會議增益集所需的軟體**

|**系統元件**|**支援的版本：**|
|:-----|:-----|
|Windows 作業系統  <br/> |Windows 10  <br/> Windows 8.1  <br/> Windows 8 <br/> Windows Server 2008 R2 或更新版本（含最新 service pack）  <br/> **附注：** Windows Vista 或 Windows XP (任何版本) 上都不支援商務用 skype 和商務用 Skype 的線上會議增益集。 <br/> |
|安裝和更新  <br/> |系統管理員的許可權  <br/> |
|瀏覽器  <br/> |Microsoft Edge  <br/> Internet Explorer 11 Internet browser  <br/>  Internet Explorer 10 Internet browser <br/> Internet Explorer 9 網際網路瀏覽器  <br/> Internet Explorer 8 網際網路瀏覽器  <br/> Internet Explorer 7 網際網路瀏覽器  <br/> Mozilla Firefox 網頁瀏覽器  <br/>  Google Chrome 網頁瀏覽器  <br/>**附注：** 如果您使用商務用 Skype 與 Microsoft Exchange Online，而且您的組織已部署驗證 HTTP proxy，則需要 Internet Explorer 8 或更新版本。           |
|Microsoft Office 整合  <br/> | Outlook 2010 或更新版本 |
|Microsoft Exchange 整合  <br/> | Microsoft Exchange Server 2010 或更新版本  | 
   
## <a name="hardware"></a>硬體

如需執行商務用 Skype 用戶端所需的硬體，請參閱 Microsoft 365 和 Office [系統需求](https://products.office.com/office-system-requirements) 。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 會議應用程式和商務用 Skype Web App 

Skype 會議應用程式和商務用 Skype Web App 支援特定的作業系統和瀏覽器混合。 如需詳細資訊，請參閱 [Plan For meeting 客戶 (Web App 和會議應用程式) ](meetings-clients.md)。 
  
## <a name="using-mandatory-profiles"></a>使用強制設定檔

如果您打算使用商務用 Skype 會議功能，請避免使用 Active Directory 網域服務強制設定檔登入商務用 Skype 用戶端。 由於強制設定檔是唯讀的使用者設定檔，因此無法將商務用 Skype 會議所需的公開金鑰基礎結構 (PKI) 機碼儲存至設定檔。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>商務用 Skype for Windows Phone 的系統需求
 
 
Microsoft 商務用 Skype for Windows Phone 為組織中從 smartphone 或 Windows 專業行動裝置連線的使用者，提供立即訊息 (IM) 、增強型目前狀態和電話語音。 行動裝置可讓使用者擴充商務用 Skype 的範圍。 本主題說明 Windows Phone 商務用 Skype 的規劃考慮，包括識別必要條件和技術需求、必要元件，以及部署指導。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone 的商務用 Skype 先決條件

以下是適用于 Windows Phone 必要條件的商務用 Skype。
  
- Windows Phone 8.1 或更新版本。
    
- Windows Phone 裝置必須具備可供 Microsoft 使用的最新更新。 如需詳細資訊，請參閱 windows [phone 8 更新歷程記錄](https://go.microsoft.com/fwlink/p/?LinkID=281961)中的 windows phone 8.1 區段。
    
- 裝置必須有 22 MB 的可用磁碟空間。
    
- 使用者必須具備來自電信公司的語音和通話方案。


## <a name="see-also"></a>另請參閱

[規劃會議用戶端 (Web 應用程式和會議應用程式) ](meetings-clients.md)
  
[Mac 用戶端需求的商務用 Skype](mac-requirements.md)

[在所有裝置中下載商務用 Skype](https://products.office.com/skype-for-business/download-app?tab=tabs-3)
  
[Microsoft 365 和 Office 系統需求](https://products.office.com/office-system-requirements)
