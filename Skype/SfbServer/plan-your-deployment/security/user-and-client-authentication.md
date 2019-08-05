---
title: 商務用 Skype Server 的使用者和用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任的使用者是認證已由商務用 Skype Server 中的受信任伺服器進行驗證的人。 此伺服器通常是標準版 server、Enterprise Edition 前端伺服器或控制器。 商務用 Skype Server 依賴 Active Directory 網域服務做為使用者認證的單一、受信任後端儲存庫。
ms.openlocfilehash: 35d1c6861ba8863e308939997fd802d4abcea404
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192932"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="b85e6-105">商務用 Skype Server 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="b85e6-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="b85e6-106">受信任的使用者是認證已由商務用 Skype Server 中的受信任伺服器進行驗證的人。</span><span class="sxs-lookup"><span data-stu-id="b85e6-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="b85e6-107">此伺服器通常是標準版 server、Enterprise Edition 前端伺服器或控制器。</span><span class="sxs-lookup"><span data-stu-id="b85e6-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="b85e6-108">商務用 Skype Server 依賴 Active Directory 網域服務做為使用者認證的單一、受信任後端儲存庫。</span><span class="sxs-lookup"><span data-stu-id="b85e6-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="b85e6-109">驗證是將使用者認證提供給信任的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b85e6-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="b85e6-110">商務用 Skype 伺服器會根據使用者的狀態和位置, 使用下列驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="b85e6-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="b85e6-111">針對具有 Active Directory 認證的內部使用者, **MIT Kerberos 版本5安全通訊協定**。</span><span class="sxs-lookup"><span data-stu-id="b85e6-111">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="b85e6-112">Kerberos 需要用戶端連線至 Active Directory 網域服務, 這就是為什麼它無法用來驗證公司防火牆外部的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b85e6-112">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="b85e6-113">適用于使用者的**NTLM 通訊協定**, 其 Active Directory 認證是從公司防火牆以外的端點連線。</span><span class="sxs-lookup"><span data-stu-id="b85e6-113">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="b85e6-114">[存取邊緣服務] 會將登入要求傳到主管 (如果有的話), 或傳遞給前端伺服器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b85e6-114">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="b85e6-115">存取邊緣服務本身不會執行任何驗證。</span><span class="sxs-lookup"><span data-stu-id="b85e6-115">The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b85e6-116">NTLM 通訊協定提供的防護防護功能不夠安全, 因此有些組織會將 NTLM 的使用量降至最低。</span><span class="sxs-lookup"><span data-stu-id="b85e6-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="b85e6-117">因此, 存取商務用 Skype 伺服器的方式可能會限制為內部或透過 VPN 或 DirectAccess 連線進行連線的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b85e6-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="b85e6-118">稱為匿名使用者的**摘要通訊協定**。</span><span class="sxs-lookup"><span data-stu-id="b85e6-118">**Digest protocol** for so-called anonymous users.</span></span> <span data-ttu-id="b85e6-119">匿名使用者是指沒有辨識 Active Directory 認證但受邀者加入內部部署會議, 且擁有有效會議金鑰的使用者。</span><span class="sxs-lookup"><span data-stu-id="b85e6-119">Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key.</span></span> <span data-ttu-id="b85e6-120">[摘要式驗證] 不用於其他用戶端互動。</span><span class="sxs-lookup"><span data-stu-id="b85e6-120">Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="b85e6-121">商務用 Skype 伺服器驗證是由兩個階段組成:</span><span class="sxs-lookup"><span data-stu-id="b85e6-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="b85e6-122">在用戶端與伺服器之間建立安全關聯。</span><span class="sxs-lookup"><span data-stu-id="b85e6-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="b85e6-123">用戶端和伺服器使用現有的安全性關聯來簽署其傳送的訊息, 並驗證收到的訊息。</span><span class="sxs-lookup"><span data-stu-id="b85e6-123">The client and server use the existing security association to sign messages that they send and to verify the messages they receive.</span></span> <span data-ttu-id="b85e6-124">在伺服器上啟用驗證時, 不會接受來自用戶端的未驗證訊息。</span><span class="sxs-lookup"><span data-stu-id="b85e6-124">Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="b85e6-125">使用者信任已附加至源于使用者的每一封郵件, 而不是使用者身分識別本身。</span><span class="sxs-lookup"><span data-stu-id="b85e6-125">User trust is attached to each message that originates from a user, not to the user identity itself.</span></span> <span data-ttu-id="b85e6-126">伺服器會檢查每一封郵件是否有有效的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="b85e6-126">The server checks each message for valid user credentials.</span></span> <span data-ttu-id="b85e6-127">如果使用者認證有效, 則除了由第一個伺服器來接收郵件, 但在受信任的伺服器雲端中, 所有其他伺服器, 都不會 unchallenged 該郵件。</span><span class="sxs-lookup"><span data-stu-id="b85e6-127">If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="b85e6-128">具有聯盟夥伴所頒發之有效認證的使用者是受信任的, 但其他限制式可讓您享受完整的許可權 accorded 給內部使用者。</span><span class="sxs-lookup"><span data-stu-id="b85e6-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="b85e6-129">[ICE] 和 [轉換] 通訊協定也會使用 [摘要式轉換 RFC] 中所述的摘要問題。</span><span class="sxs-lookup"><span data-stu-id="b85e6-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="b85e6-130">用戶端憑證為使用者提供由商務用 Skype 伺服器驗證的替代方法。</span><span class="sxs-lookup"><span data-stu-id="b85e6-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="b85e6-131">使用者不會提供使用者名稱和密碼, 而是會有一個憑證和私密金鑰對應至解決密碼質詢所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="b85e6-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="b85e6-132">(此憑證必須有識別使用者且必須由執行商務用 Skype Server 的伺服器所信任之根 CA 所頒發, 請在證書的有效期內, 且未被吊銷。)若要進行驗證, 使用者只需要輸入個人識別碼 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="b85e6-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="b85e6-133">憑證對於電話、行動電話及其他難以輸入使用者名稱和密碼的裝置非常有用。</span><span class="sxs-lookup"><span data-stu-id="b85e6-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="b85e6-134">ASP .NET 4.5 的加密需求</span><span class="sxs-lookup"><span data-stu-id="b85e6-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="b85e6-135">從商務用 Skype Server 2015 CU5, 不支援 ASP.NET 4.6 的 AES, 這可能會導致 Skype 會議應用程式無法啟動。</span><span class="sxs-lookup"><span data-stu-id="b85e6-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="b85e6-136">如果用戶端使用的是 AES 作為電腦金鑰驗證值, 您將需要在 IIS 上的 Skype 會議應用程式網站層級將電腦金鑰值重設為 SHA-1 或其他支援的演算法。</span><span class="sxs-lookup"><span data-stu-id="b85e6-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="b85e6-137">如有需要, 請參閱[IIS 8.0 ASP.NET 設定管理](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="b85e6-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="b85e6-138">其他支援的值為:</span><span class="sxs-lookup"><span data-stu-id="b85e6-138">Other supported values are:</span></span>
  
- <span data-ttu-id="b85e6-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="b85e6-139">HMACSHA256</span></span>
    
- <span data-ttu-id="b85e6-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="b85e6-140">HMACSHA384</span></span>
    
- <span data-ttu-id="b85e6-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="b85e6-141">HMACSHA512</span></span>
    
  <span data-ttu-id="b85e6-142">我們不再允許使用值 AES、3DES 和 MD5, 就像在 ASP.NET 4 中一樣。</span><span class="sxs-lookup"><span data-stu-id="b85e6-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="b85e6-143">[ASP.NET 4.5, pt 中的密碼增強功能](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)有更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b85e6-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
  
