---
title: 設定 Microsoft Teams 會議室的帳戶
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
description: 請閱讀本主題以瞭解在 Exchange 和商務用 Skype 中為 Microsoft Teams 會議室進行帳戶的組組。
ms.openlocfilehash: 26879b2c07b859e65255ed84bedd4897b75d5caa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117471"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>設定 Microsoft Teams 會議室的帳戶
 
請閱讀本主題以瞭解 Microsoft Teams 會議室及其如何與 Exchange 和商務用 Skype 整合。
  
本主題將介紹如何在 Microsoft Exchange 和商務用 Skype 中建立 Microsoft Teams 會議室所使用的帳戶。 Microsoft Teams 會議室裝置部署指示涵蓋在設定 [Microsoft Teams 會議室主控台中](console.md)。 您的基礎結構可能會屬於下列其中一種配置：
  
- 線上部署：貴組織的環境完全部署在 Microsoft 365 或 Office 365 上。 詳細資訊請參閱使用 [Microsoft 365 或 Office 365](with-office-365.md)部署 Microsoft Teams 會議室。
    
- 內部部署：貴組織有它所控制的伺服器，其中 Active Directory、Exchange 和商務用 Skype Server 是託管伺服器。 詳細資訊，請參閱使用[商務用 Skype Server](with-skype-for-business-server-2015.md)部署 Microsoft Teams 會議室
    
- 混合式部署：貴組織有混合式服務，有些是內部部署，有些則透過 Microsoft 365 或 Office 365 在線上託管。 Microsoft Teams 會議室支援下列混合式案例：
    
  - 內部部署商務用 Skype Server 的 Exchange Online。 詳細資訊，請參閱使用[Exchange Online 部署 Microsoft Teams 會議室 (混合式) 。](with-exchange-online.md)
    
  - 使用 Microsoft Teams 或商務用 Skype Online 在內部部署中交換。 詳細資訊，請參閱在內部部署 Exchange 部署[Microsoft Teams 會議室 (混合式) 。](with-exchange-on-premises.md)
    
您擁有哪些設定將會影響您準備裝置設定時如何進行。
  
Microsoft Teams 會議室需要在 Active Directory、Exchange 和商務用 Skype 中指派「裝置帳戶」。 該帳戶可用來存取其會議日曆並建立 Microsoft Teams 或商務用 Skype 的連接。 人員可以預約此帳戶，並排程會議。 Microsoft Teams 會議室將能夠加入該會議，並提供各種功能給會議出席者。
  
> [!IMPORTANT]
> 沒有裝置帳戶，這些功能都不起作用。 
  
每個裝置帳戶都是單一 Microsoft Teams 會議室裝置所特有的，而且需要一些設定：
  
- 裝置帳戶必須正確配置。
    
- 您的基礎結構必須配置為允許 Microsoft Teams 會議室驗證裝置帳戶，並取得適當的 Microsoft 服務。
    
> [!IMPORTANT]
> 強烈建議在實際硬體安裝之前先完成帳戶建立。 在理想情況下，帳戶準備是在安裝前兩到三周開始。 

在混合式環境中，用於 Microsoft Teams 會議室的帳戶必須在 Azure Active Directory (AAD) 同步) 啟用密碼同步，因為 Microsoft Teams 會議室驗證需要 Microsoft 365 或 Office 365 驗證。 設定帳戶時，請確認帳戶的 SIP 位址與 AAD 中的使用者主體名稱 (UPN) 一起。 
  
您可以將裝置帳戶視為資源帳戶，而使用者可以將該帳戶視為會議室或會議空間的帳戶。 當您想要使用該會議室排程會議時，請邀請帳戶加入該會議。 若要最有效地使用 Microsoft Teams 會議室，請對指派給每個會議室的裝置帳戶執行相同的操作。
  
如果您已經針對要安裝 Microsoft Teams 會議室的會議空間設定資源信箱帳戶，您可以將該資源帳戶變更為裝置帳戶。 完成後，您只需要將裝置帳戶新增到 Microsoft Teams 會議室裝置。 請參閱下方提供的裝置帳戶設定範例。
  
使用其他組組時，您可以如規劃 Microsoft Teams 會議室管理與 Azure 監視器、使用[Azure](azure-monitor-deploy.md)監視器部署 Microsoft Teams 會議室管理，以及使用 Azure 監視器管理 Microsoft [Teams](azure-monitor-plan.md)會議室裝置中所述，使用 Microsoft Azure 監視器進行遠端[管理](azure-monitor-manage.md)。 
  
## <a name="basic-configuration"></a>基本組組

這些屬性代表裝置帳戶使用 Microsoft Teams 會議室的最低組組。 您的裝置帳戶可能需要進一步設定。
  
|**屬性**|**目的**|
|:-----|:-----|
|Exchange 信箱 (Exchange 2013 SP1 或更高版本，或 Exchange Online)   <br/> |使用 Exchange 信箱啟用帳戶，讓裝置帳戶能夠接收及傳送郵件和會議要求，以及顯示 Microsoft Teams 會議室裝置上的會議日曆。 Microsoft Teams 會議室信箱必須是會議室信箱。  <br/> |
|已啟用商務用 Skype  <br/> |商務用 Skype 必須啟用，才能使用各種會議功能，例如視像通話、IM 和螢幕分享。 同時支援商務用 Skype Online 和商務用 Skype Server。  <br/> |
|啟用密碼  <br/> |裝置帳戶必須使用密碼啟用，或無法使用 Exchange 或商務用 Skype Server 進行驗證。  <br/> |
   
## <a name="advanced-configuration"></a>進位組

雖然基本設定的屬性會允許在簡單的環境中設定裝置帳戶，但您的環境可能對於目錄帳戶有其他限制，Microsoft Teams 會議室才能順利使用裝置帳戶。
  
|**屬性**|**目的**|
|:-----|:-----|
|憑證式驗證  <br/> |Exchange 和商務用 Skype Server 可能需要憑證。 若要部署憑證，您可以在以系統管理員登入時載入憑證。  <br/> |
   
設定裝置帳戶最簡單的方法是使用遠端 Windows PowerShell 來設定它們。 Microsoft 提供 [SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新裝置帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為相容的 Microsoft Teams 會議室裝置帳戶。
  
如果您想要使用 Microsoft 365 或 Office 365 UI，而不想使用 Windows PowerShell Cmdlet，可以手動執行一些步驟。 請參閱 [使用 Microsoft 365 或 Office 365 建立裝置帳戶](/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另請參閱

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)