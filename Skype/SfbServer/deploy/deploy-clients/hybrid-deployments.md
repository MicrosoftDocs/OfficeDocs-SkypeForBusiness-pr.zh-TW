---
title: Skype 室系統混合式部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 閱讀此主題以瞭解如何在混合式環境中部署 Skype 室系統。
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219673"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype 室系統混合式部署

閱讀此主題以瞭解如何在混合式環境中部署 Skype 室系統。
  
## <a name="hybrid-deployments"></a>混合式部署

如果您的拓撲具有商務用 Skype 伺服器和 Exchange Online，而且您想要在 Exchange Online 上裝載 Skype 會議室系統資源信箱，請遵循下列步驟。 本節也涵蓋同時部署 Exchange Online 和 Exchange 伺服器的混合式案例。
  
出於說明目的，我們會針對線上網域使用內部部署網域和 LyncSample.ccstp.net 的 LyncSample.com。
  
1. 連線至 exchange online 管理命令介面（如 Exchange Online 布建中所述），以在 Exchange 系統管理中心建立資源信箱（LyncSample.ccsctp.net）。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    您可以使用 lrstest5@LyncSample.ccsctp.net 來驗證 OWA 連線性，以登入。
    
2. 在 Microsoft 365 或 Office 365 Exchange 系統管理中心中，新增電子郵件地址 lrstest5@LyncSample.com （部署網域），並將其設為回復位址。
    
3. 建立部署 Active Directory 使用者 lrstest5@LyncSample.com，將電子郵件地址設定為 lrstest5@LyncSample.com，並將目標位址設定為 lrstest5@LyncSample.com。
    
4. 觸發目錄同步處理，而且在同步處理完成後，請確認使用者在 AAD 中合併，且您無法變更 Microsoft 365 或 Office 365 Exchange 系統管理中心中收件者資源的屬性。
    
5. 使用 lrstest5@LyncSample.com 驗證 OWA 連線。 （稍舊，您使用線上網域驗證 OWA 連線。）
    
    在建立信箱之後，您可以在 Exchange Online 管理命令介面上使用 Set-CalendarProcessing 來設定信箱。 如需詳細資訊，請參閱部署部署的單一樹系中的步驟3到6。
    
   > [!NOTE]
   > 如果您有 Exchange Server 和 Exchange Online 的混合式環境，請移至 Exchange 管理命令介面，並 Enable-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net。 然後觸發目錄同步處理。 
  
    如果您想要在 Exchange Online 中主控 Skype 室系統信箱，則不需要這些 Exchange 管理命令介面步驟，您可以繼續進行步驟6。
    
6. 在商務用 Skype 管理命令介面上執行下列 Cmdlet，為商務用 skype 啟用商務用 skype 系統帳戶：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 在上述案例中，如果您有商務用 Skype Online，而不是商務用 Skype Server，請在布建 Exchange 資源信箱之後，依照商務用 Skype Online 布妥中所述，布建商務用 skype 帳戶。 
  

