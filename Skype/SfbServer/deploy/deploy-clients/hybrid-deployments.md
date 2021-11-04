---
title: Skype會議室系統混合式部署
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 閱讀此主題以瞭解如何在混合式環境中部署 Skype 的會議室系統。
ms.openlocfilehash: c47809fcf5277ed34f11955b19306e6a4078d650
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751352"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype會議室系統混合式部署

閱讀此主題以瞭解如何在混合式環境中部署 Skype 的會議室系統。
  
## <a name="hybrid-deployments"></a>混合式部署

如果拓撲已商務用 Skype Server 和 Exchange Online，且您想要將 Skype 的會議室系統資源信箱裝載于 Exchange Online 上，請遵循下列步驟。 本節也涵蓋同時部署 Exchange Online 和 Exchange Server 的混合式案例。
  
出於說明目的，我們會針對線上網域使用內部部署網域和 LyncSample.ccstp.net 的 LyncSample.com。
  
1. 透過 Exchange Online 布建中所述，以連線至 Exchange Online 管理命令介面，在 Exchange 系統管理中心建立資源信箱 (LyncSample.ccsctp.net) 。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    您可以使用 lrstest5@LyncSample.ccsctp.net 來驗證 OWA 連線性，以登入。
    
2. 在 Microsoft 365 或 Office 365 Exchange 系統管理中心] 中，新增電子郵件地址 lrstest5@LyncSample.com (部署網域) ，然後將其設為回復位址。
    
3. 建立部署 Active Directory 使用者 lrstest5@LyncSample.com，將電子郵件地址設定為 lrstest5@LyncSample.com，並將目標位址設定為 lrstest5@LyncSample.com。
    
4. 觸發目錄同步處理，而且在同步處理完成後，請確認使用者在 AAD 中合併，而且無法在 Microsoft 365 或 Office 365 Exchange 系統管理中心中變更收件者資源中的屬性。
    
5. 使用 lrstest5@LyncSample.com 驗證 OWA 連線。  (早些時候，您已使用線上網域驗證 OWA 連線。 ) 
    
    在建立信箱之後，您可以在 Exchange Online 管理命令介面上使用 Set-CalendarProcessing 來設定信箱。 如需詳細資訊，請參閱部署部署的單一樹系中的步驟3到6。
    
   > [!NOTE]
   > 如果您有 Exchange Server 和 Exchange Online 的混合式環境，請移至 Exchange 管理命令介面及 Enable-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net。 然後觸發目錄同步處理。 
  
    如果您想要在 Exchange Online 中主控 Skype 的會議室系統信箱，則不需要這些 Exchange 管理命令介面步驟，您可以繼續進行步驟6。
    
6. 在商務用 Skype 管理命令介面上執行下列 Cmdlet，以啟用商務用 Skype 的 Skype 會議室系統帳戶：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 若您在上述案例中商務用 Skype Online，而不是商務用 Skype Server，請在布建 Exchange 資源信箱之後，依照商務用 Skype 線上布建中所述，供應商務用 Skype 帳戶。 
  

