---
title: 商務用 Skype Server 的使用者和用戶端驗證
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任的使用者是指其認證已由商務用 Skype Server 中的受信任伺服器驗證的使用者。 在大部分的情況下，此伺服器可能是 Standard Edition Server、Enterprise Edition 前端伺服器或 Director。 商務用 Skype 伺服器依賴 Active Directory 網域服務做為使用者認證的單一、信任的後端存放庫。
ms.openlocfilehash: 544b661523bea73d65d64946d7bb88d4c6ecaa51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120885"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="ae537-105">商務用 Skype Server 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="ae537-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="ae537-106">受信任的使用者是指其認證已由商務用 Skype Server 中的受信任伺服器驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="ae537-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="ae537-107">在大部分的情況下，此伺服器可能是 Standard Edition Server、Enterprise Edition 前端伺服器或 Director。</span><span class="sxs-lookup"><span data-stu-id="ae537-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="ae537-108">商務用 Skype 伺服器依賴 Active Directory 網域服務做為使用者認證的單一、信任的後端存放庫。</span><span class="sxs-lookup"><span data-stu-id="ae537-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="ae537-109">驗證是將使用者憑證佈建到受信任伺服器的歷程。</span><span class="sxs-lookup"><span data-stu-id="ae537-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="ae537-110">商務用 Skype 伺服器使用下列驗證通訊協定，視使用者的狀態和位置而定。</span><span class="sxs-lookup"><span data-stu-id="ae537-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="ae537-p104">**MIT Kerberos 5 安全性通訊協定**：用於具有 Active Directory 認證的內部使用者。Kerberos 需要用戶端連線至 Active Directory 網域服務，這也是為什麼它無法用來驗證企業防火牆外部的用戶端。</span><span class="sxs-lookup"><span data-stu-id="ae537-p104">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="ae537-p105">**NTLM 通訊協定**：用於具有 Active Directory 認證，並且從企業防火牆外部端點連線的使用者。Access Edge Service 會將登入要求傳遞至 Director (如果存在) 或是前端伺服器進行驗證。Access Edge Service 本身不執行驗證工作。</span><span class="sxs-lookup"><span data-stu-id="ae537-p105">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae537-116">NTLM 通訊協定所提供的攻擊防護較 Kerberos 弱，因此部分組織會盡量少用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="ae537-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="ae537-117">因此，對商務用 Skype 伺服器的存取權可能限制為內部或透過 VPN 或 DirectAccess 連線所連接的用戶端。</span><span class="sxs-lookup"><span data-stu-id="ae537-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="ae537-p107">**摘要式通訊協定**：用於所謂的匿名使用者。匿名使用者是沒有認可的 Active Directory 認證，但受邀參加內部會議且擁有有效會議金鑰的外部使用者。摘要式驗證並非用以與其他用戶端互動。</span><span class="sxs-lookup"><span data-stu-id="ae537-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="ae537-121">商務用 Skype Server 驗證封裝含兩個階段：</span><span class="sxs-lookup"><span data-stu-id="ae537-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="ae537-122">用戶端和伺服器之間會建立安全性關聯。</span><span class="sxs-lookup"><span data-stu-id="ae537-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="ae537-p108">用戶端和伺服器會使用現有的安全性關聯，簽署所傳送的訊息，並驗證接收的訊息。伺服器啟用驗證時，並不會接受來自用戶端的任何未驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="ae537-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="ae537-p109">使用者信任是附加於每個使用者發出的訊息中，而不是附加於使用者的識別證明上。伺服器會檢查每個訊息，看看是否具有有效的使用者憑證。如果使用者憑證有效，不但接收訊息的第一個伺服器不會驗證訊息，受信任伺服器 Cloud 中的所有伺服器也都不會驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="ae537-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="ae537-128">具有同盟夥伴所發出之有效認證的使用者會受到信任，但是可能會選擇性地受到其他限制，而無法享有與內部使用者相同的完整權限。</span><span class="sxs-lookup"><span data-stu-id="ae537-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="ae537-129">ICE 和 TURN 通訊協定也會使用 IETF TURN RFC 中所述的摘要式挑戰。</span><span class="sxs-lookup"><span data-stu-id="ae537-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="ae537-130">用戶端憑證提供另一種方式，以供商務用 Skype Server 驗證使用者。</span><span class="sxs-lookup"><span data-stu-id="ae537-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="ae537-131">使用者會具備解析密碼編譯挑戰所需之對應憑證的憑證和私密金鑰，而不是提供使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="ae537-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="ae537-132"> (此憑證必須具有識別使用者的主體名稱或主體替代名稱，且必須由執行商務用 Skype Server 之伺服器所信任的根 CA 所發出，請在憑證的有效期限內，且未被吊銷。 ) 若要進行驗證，使用者只需要輸入個人識別碼 (PIN) 。</span><span class="sxs-lookup"><span data-stu-id="ae537-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="ae537-133">憑證對電話、行動電話和其他裝置特別有用，因為這很難輸入使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="ae537-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="ae537-134">由於 ASP .NET 4.5 的加密需求</span><span class="sxs-lookup"><span data-stu-id="ae537-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="ae537-135">在商務用 Skype Server 2015 CU5 中，不支援 ASP.NET 4.6 的 AES，這可能會導致 Skype 會議應用程式無法啟動。</span><span class="sxs-lookup"><span data-stu-id="ae537-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="ae537-136">如果用戶端使用 AES 做為電腦金鑰驗證值，您需要在 IIS 的 Skype 會議應用程式網站層級將電腦金鑰值重設為 SHA-1 或其他支援的演算法。</span><span class="sxs-lookup"><span data-stu-id="ae537-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="ae537-137">如有必要，請參閱 [IIS 8.0 ASP.NET 設定管理](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) 以取得指示。</span><span class="sxs-lookup"><span data-stu-id="ae537-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="ae537-138">其他支援的值包括：</span><span class="sxs-lookup"><span data-stu-id="ae537-138">Other supported values are:</span></span>
  
- <span data-ttu-id="ae537-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="ae537-139">HMACSHA256</span></span>
    
- <span data-ttu-id="ae537-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="ae537-140">HMACSHA384</span></span>
    
- <span data-ttu-id="ae537-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="ae537-141">HMACSHA512</span></span>
    
  <span data-ttu-id="ae537-142">不允許使用 AES、3DES 和 MD5 值，就像在 ASP.NET 4 中那樣。</span><span class="sxs-lookup"><span data-stu-id="ae537-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="ae537-143">[ASP.NET 4.5，pt 中的加密增強功能](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) 會有更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ae537-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
