---
title: Skype 室系統混合式部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 若要瞭解如何在混合式環境中部署 Skype 會議室系統, 請閱讀本主題。
ms.openlocfilehash: 37ed625ca97ba34a30ec6f4acbabce272ef6ac50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192507"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype 室系統混合式部署

若要瞭解如何在混合式環境中部署 Skype 會議室系統, 請閱讀本主題。
  
## <a name="hybrid-deployments"></a>混合式部署

如果您的拓撲具有商務用 Skype Server 和 Exchange Online, 且您想要在 Exchange Online 上裝載 Skype 會議室系統資源信箱, 請遵循下列步驟。 本節也涵蓋您同時部署 Exchange Online 和 Exchange Server 的混合式案例。
  
針對說明用途, 我們將 LyncSample.com 用於內部部署網域, 並 LyncSample.ccstp.net online 網域。
  
1. 若要在 Exchange Online 管理命令介面 (LyncSample.ccsctp.net) 中建立資源信箱, 請參閱 Exchange Online 提供中的說明。
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    您可以使用 lrstest5@LyncSample.ccsctp.net 驗證 OWA 連線性, 以登入。
    
2. 在 Office 365 Exchange 系統管理中心中, 新增電子郵件地址 lrstest5@LyncSample.com (在內部部署網域上), 並將其設定為回復位址。
    
3. 建立內部部署 Active Directory 使用者 lrstest5@LyncSample.com、將電子郵件地址設定為 lrstest5@LyncSample.com, 然後將目標位址設定為 lrstest5@LyncSample.com。
    
4. 觸發目錄同步處理, 並在同步處理完成後, 確認使用者在 AAD 中進行合併, 且您無法在 Office365 Exchange 系統管理中心的收件者資源中變更屬性。
    
5. 使用 lrstest5@LyncSample.com 驗證 OWA 連線。 (較舊的版本), 您是使用線上網域驗證 OWA 連線性。)
    
    建立信箱之後, 您可以在 Exchange Online 管理命令介面上使用 [CalendarProcessing] 來設定信箱。 如需詳細資訊, 請參閱單一目錄林內部部署部署底下的步驟3到6。
    
   > [!NOTE]
   > 如果您有混合式環境與 Exchange Server 和 Exchange Online, 請移至 Exchange 管理命令介面, 並啟用-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net。 然後觸發目錄同步處理。 
  
    如果您想要在 Exchange Online 中裝載 Skype 會議室系統信箱, 則不需要這些 Exchange 管理命令介面步驟, 您可以繼續步驟6。
    
6. 在商務用 Skype 管理命令介面上, 執行下列 Cmdlet 來啟用商務用 Skype 的 Skype 會議室系統帳戶:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果您在上述案例中有商務用 Skype Online, 而不是商務用 Skype Server, 請在建立 Exchange 資源信箱之後, 按照商務用 Skype Online 設定中所述, 供應商務用 Skype 帳戶。 
  

