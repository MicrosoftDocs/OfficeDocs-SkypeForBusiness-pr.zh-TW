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
ms.openlocfilehash: 6c9c91f1b8355c95ceb3deae5f07e5c95710d036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a>Lync Server 2013 的使用者和用戶端驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-11_

受信任的使用者是認證已由 Microsoft Lync Server 2013 中受信任伺服器驗證的使用者。 此伺服器通常是標準版 server、Enterprise Edition 前端伺服器或控制器。 Lync Server 2013 依賴 Active Directory 網域服務做為使用者認證的單一、受信任後端儲存庫。

驗證是將使用者認證提供給信任的伺服器。 Lync Server 2013 使用下列驗證通訊協定，視使用者的狀態和位置而定。

  - 針對具有 Active Directory 認證的內部使用者， **MIT Kerberos 版本5安全通訊協定**。 Kerberos 需要用戶端連線至 Active Directory 網域服務，這就是為什麼它無法用來驗證公司防火牆外部的用戶端。

  - 適用于使用者的**NTLM 通訊協定**，其 Active Directory 認證是從公司防火牆以外的端點連線。 [存取邊緣服務] 會將登入要求傳到主管（如果有的話），或傳遞給前端伺服器進行驗證。 存取邊緣服務本身不會執行任何驗證。
    
    <div>
    

    > [!NOTE]  
    > NTLM 通訊協定提供的防護防護功能不夠安全，因此有些組織會將 NTLM 的使用量降至最低。 因此，您可能會將對 Lync Server 2013 的存取許可權制在內部，或是透過 VPN 或 DirectAccess 連線進行連線的用戶端。

    
    </div>

  - 稱為匿名使用者的**摘要通訊協定**。 匿名使用者是指沒有辨識 Active Directory 認證但受邀者加入內部部署會議，且擁有有效會議金鑰的使用者。 [摘要式驗證] 不用於其他用戶端互動。

Lync Server 2013 驗證封裝含兩個階段：

1.  在用戶端與伺服器之間建立安全關聯。

2.  用戶端和伺服器使用現有的安全性關聯來簽署其傳送的訊息，並驗證收到的訊息。 在伺服器上啟用驗證時，不會接受來自用戶端的未驗證訊息。

使用者信任已附加至源于使用者的每一封郵件，而不是使用者身分識別本身。 伺服器會檢查每一封郵件是否有有效的使用者認證。 如果使用者認證有效，則除了由第一個伺服器來接收郵件，但在受信任的伺服器雲端中，所有其他伺服器，都不會 unchallenged 該郵件。

具有聯盟夥伴所頒發之有效認證的使用者是受信任的，但其他限制式可讓您享受完整的許可權 accorded 給內部使用者。

[ICE] 和 [轉換] 通訊協定也會使用 [摘要式轉換 RFC] 中所述的摘要問題。

用戶端憑證提供使用者使用 Lync Server 2013 進行驗證的替代方法。 使用者不會提供使用者名稱和密碼，而是會有一個憑證和私密金鑰對應至解決密碼質詢所需的憑證。 （這個憑證必須有識別使用者且必須由執行 Lync Server 2013 之伺服器所信任的根 CA 所頒發，請在證書的有效期內，且未被撤銷。）若要進行驗證，使用者只需要輸入個人識別碼（PIN）。 在執行 Microsoft Lync 2013 Phone Edition 的電話和其他裝置上，很難輸入使用者名稱和/或密碼，憑證特別有用。

</div>

<span> </span>

</div>

</div>

</div>

