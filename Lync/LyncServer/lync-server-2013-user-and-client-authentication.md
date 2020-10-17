---
title: Lync Server 2013：使用者和用戶端驗證
description: Lync Server 2013：使用者和用戶端驗證。
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
ms.openlocfilehash: ef545dda38e9ab4236e93df769ead393648194cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569809"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="b8c3f-103">Lync Server 2013 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="b8c3f-103">User and client authentication for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8c3f-104">_**主題上次修改日期：** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="b8c3f-104">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="b8c3f-105">受信任的使用者是指其認證已由 Microsoft Lync Server 2013 中的受信任伺服器驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-105">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b8c3f-106">在大部分的情況下，此伺服器可能是 Standard Edition Server、Enterprise Edition 前端伺服器或 Director。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-106">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="b8c3f-107">Lync Server 2013 依賴 Active Directory 網域服務做為使用者認證的單一、信任的後端存放庫。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-107">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="b8c3f-108">驗證是將使用者憑證佈建到受信任伺服器的歷程。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-108">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="b8c3f-109">Lync Server 2013 使用下列驗證通訊協定，視使用者的狀態和位置而定。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-109">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="b8c3f-p103">**MIT Kerberos 5 安全性通訊協定**：用於具有 Active Directory 認證的內部使用者。Kerberos 需要用戶端連線至 Active Directory 網域服務，這也是為什麼它無法用來驗證企業防火牆外部的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="b8c3f-p104">**NTLM 通訊協定**：用於具有 Active Directory 認證，並且從企業防火牆外部端點連線的使用者。Access Edge Service 會將登入要求傳遞至 Director (如果存在) 或是前端伺服器進行驗證。Access Edge Service 本身不執行驗證工作。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b8c3f-115">NTLM 通訊協定所提供的攻擊防護較 Kerberos 弱，因此部分組織會盡量少用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-115">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="b8c3f-116">因此，對 Lync Server 2013 的存取權可能限制為內部或透過 VPN 或 DirectAccess 連線所連接的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-116">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="b8c3f-p106">**摘要式通訊協定**：用於所謂的匿名使用者。匿名使用者是沒有認可的 Active Directory 認證，但受邀參加內部會議且擁有有效會議金鑰的外部使用者。摘要式驗證並非用以與其他用戶端互動。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="b8c3f-120">Lync Server 2013 驗證封裝含兩個階段：</span><span class="sxs-lookup"><span data-stu-id="b8c3f-120">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="b8c3f-121">用戶端和伺服器之間會建立安全性關聯。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-121">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="b8c3f-p107">用戶端和伺服器會使用現有的安全性關聯，簽署所傳送的訊息，並驗證接收的訊息。伺服器啟用驗證時，並不會接受來自用戶端的任何未驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="b8c3f-p108">使用者信任是附加於每個使用者發出的訊息中，而不是附加於使用者的識別證明上。伺服器會檢查每個訊息，看看是否具有有效的使用者憑證。如果使用者憑證有效，不但接收訊息的第一個伺服器不會驗證訊息，受信任伺服器 Cloud 中的所有伺服器也都不會驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="b8c3f-127">具有同盟夥伴所發出之有效認證的使用者會受到信任，但是可能會選擇性地受到其他限制，而無法享有與內部使用者相同的完整權限。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-127">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="b8c3f-128">ICE 和 TURN 通訊協定也會使用 IETF TURN RFC 中所述的摘要式挑戰。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-128">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="b8c3f-129">用戶端憑證為使用者提供了另一種驗證方式，以供 Lync Server 2013 驗證。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-129">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="b8c3f-130">使用者會具備解析密碼編譯挑戰所需之對應憑證的憑證和私密金鑰，而不是提供使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-130">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="b8c3f-131"> (此憑證必須具有識別使用者的主體名稱或主體替代名稱，且必須由執行 Lync Server 2013 之伺服器所信任的根 CA 所發出，請在憑證的有效期限內，且未被吊銷。 ) 若要進行驗證，使用者只需要輸入個人識別碼 (PIN) 。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-131">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="b8c3f-132">憑證對執行 Microsoft Lync 2013 Phone Edition 的電話和其他裝置特別有用，但很難輸入使用者名稱和（或）密碼。</span><span class="sxs-lookup"><span data-stu-id="b8c3f-132">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

