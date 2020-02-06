---
title: Windows 用戶端需求與軟體支援
ms.author: v-lanac
author: lanachin
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
description: 摘要：在規劃商務用 Skype Server 時，查看 Windows 用戶端支援需求。
ms.openlocfilehash: a66887b616461a40c6326a66d982a8bfbe8e9605
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803483"
---
# <a name="windows-client-requirements-and-software-support"></a>Windows 用戶端需求與軟體支援
 
**摘要：** 在規劃商務用 Skype Server 時，請查看 Windows 用戶端支援需求。
  
本節摘要說明支援商務用 Skype Windows 用戶端所需的軟體。  這些用戶端會在安裝 Office 365 時安裝，也可在[您所有裝置上的 [下載商務用 Skype](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)] 中取得。
  
> [!NOTE]
> 商務用 skype 的 [線上會議] 增益集（支援來自 Outlook 訊息與共同作業用戶端的會議管理），會自動在商務用 Skype 中安裝。 
  
**商務用 Skype 用戶端和線上會議增益集所需的軟體**

|**系統元件**|**支援的版本**|
|:-----|:-----|
|Windows 作業系統  <br/> |Windows 10  <br/> Windows 8。1  <br/> Windows 8  <br/> Windows 7 作業系統  <br/> Windows Server 2008 R2 或更新版本（含最新 service pack）  <br/> **注意：** Windows Vista 或 Windows XP （任何版本）不支援商務用 skype 與商務用 Skype 的線上會議增益集。 <br/> |
|安裝與更新  <br/> |系統管理員權利和許可權  <br/> |
|瀏覽器  <br/> |Microsoft Edge  <br/> Internet Explorer 11 網際網路瀏覽器  <br/>  Internet Explorer 10 網際網路瀏覽器 <br/> Internet Explorer 9 網際網路瀏覽器  <br/> Internet Explorer 8 網際網路瀏覽器  <br/> Internet Explorer 7 網際網路瀏覽器  <br/> Mozilla Firefox 網頁瀏覽器  <br/>  Google Chrome 網頁瀏覽器  <br/>**注意：** 如果您使用的是商務用 Skype 與 Microsoft Exchange Online，且貴組織已部署驗證 HTTP proxy，則需要 Internet Explorer 8 或更新版本。           |
|Microsoft Office 整合  <br/> | Outlook 2010 或更新版本 |
|Microsoft Exchange 整合  <br/> | Microsoft Exchange Server 2010 或更新版本  | 
   
## <a name="hardware"></a>硬體

如需執行商務用 Skype 用戶端所需的硬體，請參閱 Office 365[系統需求](https://products.office.com/en-us/office-system-requirements)。
  
## <a name="skype-meetings-app-and-skype-for-business-web-app"></a>Skype 會議應用程式和商務用 Skype Web App 

Skype 會議應用程式和商務用 Skype Web App 支援特定的作業系統與瀏覽器混合。 如需詳細資訊，請參閱[規劃會議用戶端（Web App 和會議應用程式）](meetings-clients.md)。 
  
## <a name="using-mandatory-profiles"></a>使用強制設定檔

如果您打算使用商務用 Skype 會議功能，請避免使用 Active Directory 網域服務強制性設定檔來登入商務用 Skype 用戶端。 因為強制性設定檔是唯讀的使用者設定檔，所以無法將商務用 Skype 會議所需的公開金鑰基礎結構（PKI）金鑰儲存在設定檔中。 
  
## <a name="system-requirements-for-skype-for-business-for-windows-phone"></a>Windows Phone 版商務用 Skype 的系統需求
 
 
Microsoft Windows Phone 版商務用 Skype 可為您組織中的使用者提供立即訊息（IM）、增強的目前狀態，以及使用智慧型手機或 Windows 專業行動裝置連線的電話。 行動裝置可讓使用者延伸到商務用 Skype 的範圍。 本主題說明 Windows Phone 版商務用 Skype 的規劃考慮，包括識別先決條件及技術需求、必要元件，以及部署指導方針。
  
### <a name="skype-for-business-for-windows-phone-prerequisites"></a>Windows Phone 版商務用 Skype 的先決條件

以下是 Windows Phone 版商務用 Skype 的先決條件。
  
- Windows Phone 8.1 或更新版本。
    
- Windows Phone 裝置必須具備 Microsoft 提供的最新更新。 如需詳細資訊，請參閱[Windows phone 8 更新歷程記錄](https://go.microsoft.com/fwlink/p/?LinkID=281961)中的 windows phone 8.1 區段。
    
- 裝置必須擁有 22 MB 的可用磁碟空間。
    
- 使用者必須具備來自承運人的語音和通話方案。


## <a name="see-also"></a>另請參閱

[規劃會議用戶端（Web App 與會議應用程式）](meetings-clients.md)
  
[Mac 版商務用 Skype 用戶端需求](mac-requirements.md)

[在所有裝置上下載商務用 Skype](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3)
  
[Office 365 系統需求](https://products.office.com/en-us/office-system-requirements)
