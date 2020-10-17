---
title: Lync Server 2013：使用者和用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f32ca61178d6bf15791f81e64279e7f1076828e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530200"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a>Lync Server 2013 的使用者和用戶端驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-11_

受信任的使用者是指其認證已由 Microsoft Lync Server 2013 中的受信任伺服器驗證的使用者。 在大部分的情況下，此伺服器可能是 Standard Edition Server、Enterprise Edition 前端伺服器或 Director。 Lync Server 2013 依賴 Active Directory 網域服務做為使用者認證的單一、信任的後端存放庫。

驗證是將使用者憑證佈建到受信任伺服器的歷程。 Lync Server 2013 使用下列驗證通訊協定，視使用者的狀態和位置而定。

  - **MIT Kerberos 5 安全性通訊協定**：用於具有 Active Directory 認證的內部使用者。Kerberos 需要用戶端連線至 Active Directory 網域服務，這也是為什麼它無法用來驗證企業防火牆外部的用戶端。

  - **NTLM 通訊協定**：用於具有 Active Directory 認證，並且從企業防火牆外部端點連線的使用者。Access Edge Service 會將登入要求傳遞至 Director (如果存在) 或是前端伺服器進行驗證。Access Edge Service 本身不執行驗證工作。
    
    <div>
    

    > [!NOTE]  
    > NTLM 通訊協定所提供的攻擊防護較 Kerberos 弱，因此部分組織會盡量少用 NTLM。 因此，對 Lync Server 2013 的存取權可能限制為內部或透過 VPN 或 DirectAccess 連線所連接的用戶端。

    
    </div>

  - **摘要式通訊協定**：用於所謂的匿名使用者。匿名使用者是沒有認可的 Active Directory 認證，但受邀參加內部會議且擁有有效會議金鑰的外部使用者。摘要式驗證並非用以與其他用戶端互動。

Lync Server 2013 驗證封裝含兩個階段：

1.  用戶端和伺服器之間會建立安全性關聯。

2.  用戶端和伺服器會使用現有的安全性關聯，簽署所傳送的訊息，並驗證接收的訊息。伺服器啟用驗證時，並不會接受來自用戶端的任何未驗證訊息。

使用者信任是附加於每個使用者發出的訊息中，而不是附加於使用者的識別證明上。伺服器會檢查每個訊息，看看是否具有有效的使用者憑證。如果使用者憑證有效，不但接收訊息的第一個伺服器不會驗證訊息，受信任伺服器 Cloud 中的所有伺服器也都不會驗證訊息。

具有同盟夥伴所發出之有效認證的使用者會受到信任，但是可能會選擇性地受到其他限制，而無法享有與內部使用者相同的完整權限。

ICE 和 TURN 通訊協定也會使用 IETF TURN RFC 中所述的摘要式挑戰。

用戶端憑證為使用者提供了另一種驗證方式，以供 Lync Server 2013 驗證。 使用者會具備解析密碼編譯挑戰所需之對應憑證的憑證和私密金鑰，而不是提供使用者名稱和密碼。  (此憑證必須具有識別使用者的主體名稱或主體替代名稱，且必須由執行 Lync Server 2013 之伺服器所信任的根 CA 所發出，請在憑證的有效期限內，且未被吊銷。 ) 若要進行驗證，使用者只需要輸入個人識別碼 (PIN) 。 憑證對執行 Microsoft Lync 2013 Phone Edition 的電話和其他裝置特別有用，但很難輸入使用者名稱和（或）密碼。

</div>

<span> </span>

</div>

</div>

</div>

