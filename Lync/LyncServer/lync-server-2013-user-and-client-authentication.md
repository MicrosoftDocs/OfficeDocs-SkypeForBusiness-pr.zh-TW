---
title: Lync Server 2013： 使用者與用戶端驗證
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
ms.openlocfilehash: 4dbddb0dab36a8ad805691196a00a3dc8bf6f9d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="13a7f-102">Lync Server 2013 的使用者與用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="13a7f-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13a7f-103">_**上次修改主題：** 2013年-11-11_</span><span class="sxs-lookup"><span data-stu-id="13a7f-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="13a7f-104">信任的使用者是其中一個其認證已經過驗證由 Microsoft Lync Server 2013 中受信任的伺服器。</span><span class="sxs-lookup"><span data-stu-id="13a7f-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="13a7f-105">在大部分的情況下，此伺服器可能是 Standard Edition Server、Enterprise Edition 前端伺服器或 Director。</span><span class="sxs-lookup"><span data-stu-id="13a7f-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="13a7f-106">Lync Server 2013 會依賴 Active Directory 網域服務為單一、 受信任後端儲存機制的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="13a7f-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="13a7f-107">驗證是將使用者憑證佈建到受信任伺服器的歷程。</span><span class="sxs-lookup"><span data-stu-id="13a7f-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="13a7f-108">Lync Server 2013 使用下列驗證通訊協定，根據 [狀態] 和 [使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="13a7f-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="13a7f-p103">**MIT Kerberos 5 安全性通訊協定**：用於具有 Active Directory 認證的內部使用者。Kerberos 需要用戶端連線至 Active Directory 網域服務，這也是為什麼它無法用來驗證企業防火牆外部的用戶端。</span><span class="sxs-lookup"><span data-stu-id="13a7f-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="13a7f-p104">**NTLM 通訊協定**：用於具有 Active Directory 認證，並且從企業防火牆外部端點連線的使用者。Access Edge Service 會將登入要求傳遞至 Director (如果存在) 或是前端伺服器進行驗證。Access Edge Service 本身不執行驗證工作。</span><span class="sxs-lookup"><span data-stu-id="13a7f-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="13a7f-114">NTLM 通訊協定所提供的攻擊防護較 Kerberos 弱，因此部分組織會盡量少用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="13a7f-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="13a7f-115">因此，存取 Lync Server 2013 可能會限制為內部或透過 VPN 或 DirectAccess 連線的用戶端連線。</span><span class="sxs-lookup"><span data-stu-id="13a7f-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="13a7f-p106">**摘要式通訊協定**：用於所謂的匿名使用者。匿名使用者是沒有認可的 Active Directory 認證，但受邀參加內部會議且擁有有效會議金鑰的外部使用者。摘要式驗證並非用以與其他用戶端互動。</span><span class="sxs-lookup"><span data-stu-id="13a7f-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="13a7f-119">Lync Server 2013 驗證是由兩個階段所組成：</span><span class="sxs-lookup"><span data-stu-id="13a7f-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="13a7f-120">用戶端和伺服器之間會建立安全性關聯。</span><span class="sxs-lookup"><span data-stu-id="13a7f-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="13a7f-p107">用戶端和伺服器會使用現有的安全性關聯，簽署所傳送的訊息，並驗證接收的訊息。伺服器啟用驗證時，並不會接受來自用戶端的任何未驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="13a7f-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="13a7f-p108">使用者信任是附加於每個使用者發出的訊息中，而不是附加於使用者的識別證明上。伺服器會檢查每個訊息，看看是否具有有效的使用者憑證。如果使用者憑證有效，不但接收訊息的第一個伺服器不會驗證訊息，受信任伺服器 Cloud 中的所有伺服器也都不會驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="13a7f-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="13a7f-126">具有同盟夥伴所發出之有效認證的使用者會受到信任，但是可能會選擇性地受到其他限制，而無法享有與內部使用者相同的完整權限。</span><span class="sxs-lookup"><span data-stu-id="13a7f-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="13a7f-127">ICE 和 TURN 通訊協定也會使用 IETF TURN RFC 中所述的摘要式挑戰。</span><span class="sxs-lookup"><span data-stu-id="13a7f-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="13a7f-128">用戶端憑證提供經過 Lync Server 2013 的使用者的替代方法。</span><span class="sxs-lookup"><span data-stu-id="13a7f-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="13a7f-129">使用者會具備解析密碼編譯挑戰所需之對應憑證的憑證和私密金鑰，而不是提供使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="13a7f-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="13a7f-130">（此憑證必須有主體名稱或主體替代名稱，識別使用者和必須執行 Lync Server 2013 的伺服器所信任的根 CA 所發出憑證的有效期間內，已被撤銷）。若要驗證，使用者只需要輸入個人識別碼 (PIN) 中。</span><span class="sxs-lookup"><span data-stu-id="13a7f-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="13a7f-131">憑證會特別有用的電話及其他執行 Microsoft Lync 2013 Phone Edition 很難輸入使用者名稱及/或密碼的裝置。</span><span class="sxs-lookup"><span data-stu-id="13a7f-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

