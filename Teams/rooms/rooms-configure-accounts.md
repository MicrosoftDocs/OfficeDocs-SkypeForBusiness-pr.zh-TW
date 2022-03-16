---
title: 設定帳戶Microsoft Teams 會議室
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 請閱讀本主題，瞭解如何為手機和Microsoft Teams 會議室 (手機Surface Hub) 帳戶。
ms.openlocfilehash: 4ecac71ef862fda003523bbcefe3c333daefaa23
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514728"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>設定帳戶Microsoft Teams 會議室
 
本主題將介紹如何建立帳戶Microsoft Teams 會議室。 您的基礎結構可能會屬於下列其中一種配置：
  
- 線上部署：貴組織的環境完全部署在 Microsoft 365 或 Office 365。
    
- 內部部署：貴組織有它所控制的伺服器，其中 Active Directory、Exchange和商務用 Skype Server主機。 詳細資訊，請參閱使用Microsoft Teams 會議室[部署商務用 Skype Server](with-skype-for-business-server-2015.md)
    
- 混合式部署：貴組織有混合式服務，其中一些是內部部署，有些則透過Microsoft 365或Office 365。 使用 Microsoft Teams 會議室，支援下列混合式案例：
    
  - Exchange Online內部商務用 Skype Server使用。
    
  - Exchange內部部署Microsoft Teams。
    
您擁有哪些設定將會影響您準備裝置設定時如何進行。
  
Microsoft Teams 會議室 Active Directory、Exchange，並在必要時 (資源) 商務用 Skype。 該帳戶可用來存取會議日曆並建立Microsoft Teams和/或商務用 Skype連接。 人員可以預約此帳戶，並排程會議。 Microsoft Teams 會議室加入會議，並提供各種功能給會議出席者。
  
> [!IMPORTANT]
> 沒有資源帳戶，這些功能都不起作用。
  
每個資源帳戶都是單一安裝Microsoft Teams 會議室唯一。
  
- 必須正確配置資源帳戶。
    
- 您的基礎結構必須配置為允許Microsoft Teams 會議室驗證資源帳戶，並取得適當的Microsoft 服務。

> [!NOTE] 
> 如果使用Microsoft Teams面板，Teams 會議室資源帳戶會同時Teams 會議室與相關聯的Teams面板。
    
> [!IMPORTANT]
> 強烈建議在實際硬體安裝之前先完成帳戶建立。 在理想情況下，帳戶準備是在安裝前兩到三周開始。
> 
在未使用 商務用 Skype的混合式環境中，強烈建議您以原生方式在 Azure Active Directory。 如果帳戶必須使用內部部署 Active Directory 建立，則必須在同步Azure Active Directory (AAD) 連線中啟用密碼同步Microsoft Teams 會議室驗證Microsoft 365或Office 365認證。 設定帳戶時，請確認帳戶的電子郵件地址符合其使用者主體名稱 (UPN) 中AAD。 
  
您可以將資源帳戶想像為使用者識別為會議室或共用空間名稱的帳戶。 當您想要使用該空間排程會議時，請邀請資源帳戶加入該會議。
  
如果您已經針對Exchange空間設定資源信箱帳戶Microsoft Teams 會議室，您可以將該帳戶變更為Teams 會議室帳戶。 完成之後，您只需要使用該帳戶Microsoft Teams 會議室帳戶。
  
## <a name="basic-configuration"></a>基本組組

這些屬性代表資源帳戶使用資源帳戶的最低Microsoft Teams 會議室。 您的資源帳戶可能需要進一步設定。
  
|**屬性**|**目的**|
|:-----|:-----|
|Exchange 2013 SP1 (Exchange或稍後的信箱，或Exchange Online)   <br/> |Exchange信箱提供資源帳戶接收及傳送郵件和會議要求，以及顯示會議Microsoft Teams 會議室。 Microsoft Teams 會議室信箱必須是類型為「聊天室」的資源信箱。  <br/> |
|商務用 Skype已啟用  <br/> |商務用 Skype啟用此功能，才能使用各種商務用 Skype會議功能，例如視像通話、IM 和螢幕分享。  <br/> |
|啟用密碼  <br/> |資源帳戶必須使用密碼啟用，或無法使用 Microsoft Teams、Exchange或商務用 Skype Server。 必須在所有資源帳戶上停用密碼Teams 會議室到期。   <br/> |
   
## <a name="advanced-configuration"></a>進位組

雖然基本設定的屬性會允許在簡單的環境中設定資源帳戶，但您的環境可能對於帳戶有其他限制，您必須符合這些限制，Microsoft Teams 會議室才能成功使用資源帳戶。
  
|**屬性**|**目的**|
|:-----|:-----|
|憑證式驗證  <br/> |您可能需要憑證才能Exchange商務用 Skype Server。 若要部署憑證，您可以在以系統管理員登入時載入憑證。  <br/> |

## <a name="see-also"></a>另請參閱

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
