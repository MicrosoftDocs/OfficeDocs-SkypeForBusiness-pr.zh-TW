---
title: 設定帳戶Microsoft Teams 會議室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: 請閱讀本主題，瞭解如何在 Microsoft Teams 會議室 中Exchange商務用 Skype。
ms.openlocfilehash: d66e495fd4e1e75227b162974891cda9876fef28c9f809dead001af1a95b099a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348798"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>設定帳戶Microsoft Teams 會議室
 
請閱讀本主題以瞭解Microsoft Teams 會議室，以及它如何與Exchange商務用 Skype。
  
本主題將介紹如何在 Microsoft Microsoft Teams 會議室 中建立Exchange帳戶商務用 Skype。 設定主機Microsoft Teams 會議室裝置部署指示Microsoft Teams 會議室[說明](console.md)。 您的基礎結構可能會屬於下列其中一種配置：
  
- 線上部署：貴組織的環境完全部署在 Microsoft 365 或 Office 365。 詳細資訊，請參閱使用 Microsoft Teams 會議室[或 Microsoft 365 部署Office 365。](with-office-365.md)
    
- 內部部署：貴組織有它所控制的伺服器，其中 Active Directory、Exchange 和 商務用 Skype Server是託管。 詳細資訊，請參閱使用Microsoft Teams 會議室[部署商務用 Skype Server](with-skype-for-business-server-2015.md)
    
- 混合式部署：貴組織有混合式服務，有些是內部部署，有些則透過Microsoft 365或Office 365。 使用 Microsoft Teams 會議室，支援下列混合式案例：
    
  - Exchange Online內部商務用 Skype Server中。 詳細資訊，請參閱使用混合[式Microsoft Teams 會議室部署Exchange Online () 。](with-exchange-online.md)
    
  - Exchange內部部署，Microsoft Teams或 商務用 Skype Online。 詳細資訊，請參閱在內部部署[Microsoft Teams 會議室部署Exchange混合式 (部署) 。](with-exchange-on-premises.md)
    
您擁有哪些設定將會影響您準備裝置設定時如何進行。
  
Microsoft Teams 會議室 Active Directory、Exchange和 商務用 Skype。 該帳戶可用來存取其會議日曆，並建立Microsoft Teams或商務用 Skype連接。 人員可以預約此帳戶，並排程會議。 Microsoft Teams 會議室加入會議，並提供各種功能給會議出席者。
  
> [!IMPORTANT]
> 沒有裝置帳戶，這些功能都不起作用。 
  
每個裝置帳戶都是單一裝置Microsoft Teams 會議室唯一，而且需要一些設定：
  
- 裝置帳戶必須正確配置。
    
- 您的基礎結構必須配置為允許Microsoft Teams 會議室驗證裝置帳戶，並取得適當的Microsoft 服務。
    
> [!IMPORTANT]
> 強烈建議在實際硬體安裝之前先完成帳戶建立。 在理想情況下，帳戶準備是在安裝前兩到三周開始。 

在混合式環境中，Microsoft Teams 會議室帳戶必須在 Azure Active Directory (AAD) 同步) 啟用密碼同步，因為 Microsoft Teams 會議室 驗證Microsoft 365或Office 365驗證。 設定帳戶時，請確認帳戶的 SIP 位址與 AAD 中的使用者主體名稱 (UPN) 一起。 
  
您可以將裝置帳戶視為資源帳戶，而使用者可以將該帳戶視為會議室或會議空間的帳戶。 當您想要使用該會議室排程會議時，請邀請帳戶加入該會議。 若要最Microsoft Teams 會議室，請對指派給每個帳戶的裝置帳戶執行相同的操作。
  
如果您已經針對要安裝帳戶的會議空間設定資源信箱Microsoft Teams 會議室，您可以將該資源帳戶變更為裝置帳戶。 完成之後，您只需要將裝置帳戶新增到Microsoft Teams 會議室裝置。 請參閱下方提供的裝置帳戶設定範例。
  
使用 Microsoft Azure其他組組時，您可以如規劃 Microsoft Teams 會議室 管理與[Azure 監視器](azure-monitor-plan.md)、使用 Azure 監視器部署[Microsoft Teams 會議室](azure-monitor-deploy.md)管理，以及使用 Azure 監視器管理 Microsoft Teams 會議室 裝置中所述，使用 Microsoft Teams 會議室 監視器進行遠端[管理](azure-monitor-manage.md)。 
  
## <a name="basic-configuration"></a>基本組

這些屬性代表裝置帳戶使用Microsoft Teams 會議室。 您的裝置帳戶可能需要進一步設定。
  
|**屬性**|**目的**|
|:-----|:-----|
|Exchange 2013 SP1 (Exchange或稍後的信箱，或Exchange Online)   <br/> |啟用具有信箱Exchange帳戶，讓裝置帳戶能夠接收和傳送郵件和會議要求，以及顯示 Microsoft Teams 會議室 上的會議Microsoft Teams 會議室。 Microsoft Teams 會議室信箱必須是會議室信箱。  <br/> |
|商務用 Skype已啟用  <br/> |商務用 Skype，才能使用各種會議功能，例如視像通話、IM 和螢幕分享。 同時商務用 Skype線上商務用 Skype Server支援。  <br/> |
|啟用密碼  <br/> |裝置帳戶必須使用密碼啟用，否則無法使用 Exchange 或 商務用 Skype Server。  <br/> |
   
## <a name="advanced-configuration"></a>進位組

雖然基本設定的屬性會允許裝置帳戶在簡單的環境中設定，但您的環境可能對於目錄帳戶有其他限制，Microsoft Teams 會議室 才能順利使用裝置帳戶。
  
|**屬性**|**目的**|
|:-----|:-----|
|憑證式驗證  <br/> |您可能需要憑證才能Exchange商務用 Skype Server。 若要部署憑證，您可以在以系統管理員登入時載入憑證。  <br/> |
   
設定裝置帳戶最簡單的方法是使用遠端Windows PowerShell。 Microsoft 提供[SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新裝置帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為Microsoft Teams 會議室帳戶。
  
如果您想要在 Cmdlet Microsoft 365或Office 365 UI Windows PowerShell，可以手動執行一些步驟。 請參閱[使用 Microsoft 365 或 Office 365 建立Office 365。](/surface-hub/create-a-device-account-using-office-365)
  
## <a name="see-also"></a>另請參閱

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)