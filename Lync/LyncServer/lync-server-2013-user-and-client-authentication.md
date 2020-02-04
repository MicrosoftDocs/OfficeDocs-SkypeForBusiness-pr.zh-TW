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

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="a9d00-102">Lync Server 2013 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="a9d00-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9d00-103">_**主題上次修改日期：** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="a9d00-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="a9d00-104">受信任的使用者是認證已由 Microsoft Lync Server 2013 中受信任伺服器驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9d00-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a9d00-105">此伺服器通常是標準版 server、Enterprise Edition 前端伺服器或控制器。</span><span class="sxs-lookup"><span data-stu-id="a9d00-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="a9d00-106">Lync Server 2013 依賴 Active Directory 網域服務做為使用者認證的單一、受信任後端儲存庫。</span><span class="sxs-lookup"><span data-stu-id="a9d00-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="a9d00-107">驗證是將使用者認證提供給信任的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a9d00-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="a9d00-108">Lync Server 2013 使用下列驗證通訊協定，視使用者的狀態和位置而定。</span><span class="sxs-lookup"><span data-stu-id="a9d00-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="a9d00-109">針對具有 Active Directory 認證的內部使用者， **MIT Kerberos 版本5安全通訊協定**。</span><span class="sxs-lookup"><span data-stu-id="a9d00-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="a9d00-110">Kerberos 需要用戶端連線至 Active Directory 網域服務，這就是為什麼它無法用來驗證公司防火牆外部的用戶端。</span><span class="sxs-lookup"><span data-stu-id="a9d00-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="a9d00-111">適用于使用者的**NTLM 通訊協定**，其 Active Directory 認證是從公司防火牆以外的端點連線。</span><span class="sxs-lookup"><span data-stu-id="a9d00-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="a9d00-112">[存取邊緣服務] 會將登入要求傳到主管（如果有的話），或傳遞給前端伺服器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="a9d00-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="a9d00-113">存取邊緣服務本身不會執行任何驗證。</span><span class="sxs-lookup"><span data-stu-id="a9d00-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9d00-114">NTLM 通訊協定提供的防護防護功能不夠安全，因此有些組織會將 NTLM 的使用量降至最低。</span><span class="sxs-lookup"><span data-stu-id="a9d00-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="a9d00-115">因此，您可能會將對 Lync Server 2013 的存取許可權制在內部，或是透過 VPN 或 DirectAccess 連線進行連線的用戶端。</span><span class="sxs-lookup"><span data-stu-id="a9d00-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="a9d00-116">稱為匿名使用者的**摘要通訊協定**。</span><span class="sxs-lookup"><span data-stu-id="a9d00-116">**Digest protocol** for so-called anonymous users.</span></span> <span data-ttu-id="a9d00-117">匿名使用者是指沒有辨識 Active Directory 認證但受邀者加入內部部署會議，且擁有有效會議金鑰的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9d00-117">Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key.</span></span> <span data-ttu-id="a9d00-118">[摘要式驗證] 不用於其他用戶端互動。</span><span class="sxs-lookup"><span data-stu-id="a9d00-118">Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="a9d00-119">Lync Server 2013 驗證封裝含兩個階段：</span><span class="sxs-lookup"><span data-stu-id="a9d00-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="a9d00-120">在用戶端與伺服器之間建立安全關聯。</span><span class="sxs-lookup"><span data-stu-id="a9d00-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="a9d00-121">用戶端和伺服器使用現有的安全性關聯來簽署其傳送的訊息，並驗證收到的訊息。</span><span class="sxs-lookup"><span data-stu-id="a9d00-121">The client and server use the existing security association to sign messages that they send and to verify the messages they receive.</span></span> <span data-ttu-id="a9d00-122">在伺服器上啟用驗證時，不會接受來自用戶端的未驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="a9d00-122">Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="a9d00-123">使用者信任已附加至源于使用者的每一封郵件，而不是使用者身分識別本身。</span><span class="sxs-lookup"><span data-stu-id="a9d00-123">User trust is attached to each message that originates from a user, not to the user identity itself.</span></span> <span data-ttu-id="a9d00-124">伺服器會檢查每一封郵件是否有有效的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="a9d00-124">The server checks each message for valid user credentials.</span></span> <span data-ttu-id="a9d00-125">如果使用者認證有效，則除了由第一個伺服器來接收郵件，但在受信任的伺服器雲端中，所有其他伺服器，都不會 unchallenged 該郵件。</span><span class="sxs-lookup"><span data-stu-id="a9d00-125">If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="a9d00-126">具有聯盟夥伴所頒發之有效認證的使用者是受信任的，但其他限制式可讓您享受完整的許可權 accorded 給內部使用者。</span><span class="sxs-lookup"><span data-stu-id="a9d00-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="a9d00-127">[ICE] 和 [轉換] 通訊協定也會使用 [摘要式轉換 RFC] 中所述的摘要問題。</span><span class="sxs-lookup"><span data-stu-id="a9d00-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="a9d00-128">用戶端憑證提供使用者使用 Lync Server 2013 進行驗證的替代方法。</span><span class="sxs-lookup"><span data-stu-id="a9d00-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="a9d00-129">使用者不會提供使用者名稱和密碼，而是會有一個憑證和私密金鑰對應至解決密碼質詢所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="a9d00-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="a9d00-130">（這個憑證必須有識別使用者且必須由執行 Lync Server 2013 之伺服器所信任的根 CA 所頒發，請在證書的有效期內，且未被撤銷。）若要進行驗證，使用者只需要輸入個人識別碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="a9d00-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="a9d00-131">在執行 Microsoft Lync 2013 Phone Edition 的電話和其他裝置上，很難輸入使用者名稱和/或密碼，憑證特別有用。</span><span class="sxs-lookup"><span data-stu-id="a9d00-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

