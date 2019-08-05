---
title: 設定 Microsoft 團隊聊天室的帳戶
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: 請閱讀本主題, 瞭解如何針對 Exchange 和商務用 Skype 中的 Microsoft 團隊聊天室設定帳戶。
ms.openlocfilehash: 0fe9413c8da7c50479ddceaa524813d4ab68d8c6
ms.sourcegitcommit: 3197f3ffca2b2315be9fd0c702ccc8c87383c893
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2019
ms.locfileid: "36184131"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a>設定 Microsoft 團隊聊天室的帳戶
 
請閱讀本主題以瞭解 Microsoft 團隊聊天室, 以及它如何與 Exchange 與商務用 Skype 整合。
  
本主題介紹如何在 Microsoft Exchange 和商務用 Skype 中建立 Microsoft 團隊聊天室所使用的帳戶。 Microsoft 團隊聊天室裝置的部署指示將在 [[設定 Microsoft 團隊聊天室] 主控台](console.md)中講述。 您的基礎結構可能會分為下列其中一個設定:
  
- 線上部署: 貴組織的環境會完全部署在 Office 365 上。 如需詳細資訊, 請參閱[使用 Office 365 部署 Microsoft 團隊聊天室](with-office-365.md)。
    
- 內部部署: 您的組織擁有它所控制的伺服器, 其中包含 Active Directory、Exchange 及商務用 Skype Server 的主機。 如需詳細資訊, 請參閱[使用商務用 Skype Server 部署 Microsoft 團隊聊天室](with-skype-for-business-server-2015.md)
    
- 混合式部署: 您的組織有混合式的服務, 其中一些託管于內部部署, 以及一些透過 Office 365 託管的線上。 使用 Microsoft 團隊聊天室時, 支援下列混合式案例: 
    
  - Exchange Online 與商務用 Skype Server 內部部署。 如需詳細資訊, 請參閱[使用 Exchange Online (混合式) 部署 Microsoft 團隊聊天室](with-exchange-online.md)。
    
  - 使用 Microsoft 團隊或商務用 Skype Online 在內部部署的 Exchange。 如需詳細資訊, 請參閱[使用 Exchange 內部部署 (混合式) 部署 Microsoft 團隊聊天室](with-exchange-on-premises.md)。
    
您所擁有的設定會影響您準備裝置設定的方式。
  
Microsoft 團隊聊天室需要在 Active Directory、Exchange 和商務用 Skype 中指派「裝置帳戶」。 帳戶可用來存取其會議行事曆, 並建立 Microsoft 團隊或商務用 Skype 連線。 使用者可以透過排程會議來預訂此帳戶。 Microsoft 團隊聊天室將能夠加入該會議, 並為會議出席者提供各種功能。
  
> [!IMPORTANT]
> 若沒有裝置帳戶, 這些功能都將無法運作。 
  
每個裝置帳戶對於單一 Microsoft 團隊房間裝置而言都是唯一的, 需要進行一些設定:
  
- 裝置帳戶必須設定正確。
    
- 您的基礎結構必須設定為允許 Microsoft 團隊聊天室驗證裝置帳戶, 然後才能到達適當的 Microsoft 服務。
    
> [!IMPORTANT]
> 強烈建議在實際的硬體安裝之前, 建立帳戶, 以進行良好的完成。 理想的情況是, 帳戶準備必須在安裝前兩到三周內開始。 在混合式環境中, Microsoft 團隊聊天室所用的帳戶必須在 AAD 同步處理中啟用密碼同步處理, 因為 Microsoft 團隊會議室驗證需要 Office 365 驗證。
  
您可以將裝置帳戶看作是人們辨識為會議室或會議空間帳戶的資源帳戶。 當您想要使用該會議室排程會議時, 您邀請該帳戶加入該會議。 若要最有效地使用 Microsoft 團隊聊天室, 您可以對指派給它們的裝置帳戶執行相同的動作。
  
如果您已為安裝 Microsoft 團隊聊天室的會議空間設定資源信箱帳戶, 您可以將該資源帳戶變更為裝置帳戶。 完成後, 您只需將裝置帳戶新增至 Microsoft 團隊聊天室裝置即可。 請參閱下列提供的裝置帳戶設定範例。
  
有了其他設定, 就可以使用 Microsoft Azure 監視器來[規劃 microsoft 的小組聊天室管理](azure-monitor-plan.md), 使用 azure 監視器來[部署 microsoft 團隊聊天室](azure-monitor-deploy.md)管理, 以及[使用 Azure 監視器管理 Microsoft 團隊聊天室裝置](azure-monitor-manage.md)。 
  
## <a name="basic-configuration"></a>基本設定

這些屬性代表與 Microsoft 團隊聊天室搭配使用之裝置帳戶的最小設定。 您的裝置帳戶可能需要進一步設定。
  
|**Property**|**特殊**|
|:-----|:-----|
|Exchange 信箱 (Exchange 2013 SP1 或更新版本, 或是 Exchange Online)  <br/> |啟用具有 Exchange 信箱的帳戶可讓裝置帳戶能夠接收並傳送郵件和會議邀請, 以及在 Microsoft 團隊聊天室裝置上顯示會議行事曆。 Microsoft 團隊聊天室信箱必須是會議室信箱。  <br/> |
|已啟用商務用 Skype  <br/> |必須啟用商務用 Skype, 才能使用各種會議功能, 例如, 影片通話、IM 和螢幕畫面分享。 支援商務用 Skype Online 與商務用 Skype 伺服器。  <br/> |
|已啟用密碼  <br/> |裝置帳戶必須以密碼啟用, 否則無法使用 Exchange 或商務用 Skype 伺服器進行驗證。  <br/> |
   
## <a name="advanced-configuration"></a>[高級設定]

雖然基本設定的屬性可以讓裝置帳戶在簡單的環境中設定, 但您的環境可能對目錄帳戶有其他限制, 而您必須滿足這些帳戶, Microsoft 團隊聊天室才能成功使用[裝置帳戶]。
  
|**Property**|**特殊**|
|:-----|:-----|
|以憑證為基礎的驗證  <br/> |Exchange 和商務用 Skype Server 都可能需要證書。 若要部署憑證, 您可以在以系統管理員身分登入時載入證書。  <br/> |
   
設定裝置帳戶最簡單的方法, 就是使用遠端 Windows PowerShell 加以設定。 Microsoft 提供[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), 此腳本將協助您建立新的裝置帳戶, 或驗證現有的資源帳戶, 以協助您將它們轉換成相容的 Microsoft 團隊聊天室裝置帳戶。
  
如果您想要在 Windows PowerShell Cmdlet 上使用 Office 365 UI, 可以手動執行一些步驟。 請參閱[使用 Office 365 建立裝置帳戶](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另請參閱

[規劃 Microsoft 團隊聊天室](skype-room-systems-v2-0.md)
  
[設定 Microsoft 團隊聊天室主控台](console.md)
  
[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)

