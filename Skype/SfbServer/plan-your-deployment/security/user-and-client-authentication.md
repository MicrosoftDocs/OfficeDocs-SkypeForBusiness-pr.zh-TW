---
title: 商務用 Skype Server 的使用者和用戶端驗證
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任的使用者是指其認證已由商務用 Skype Server 中的受信任伺服器驗證的使用者。 在大部分的情況下，此伺服器可能是 Standard Edition Server、Enterprise Edition 前端伺服器或 Director。 商務用 Skype Server 依賴 Active Directory 網域服務做為使用者認證的單一、受信任的後端存放庫。
ms.openlocfilehash: c0c64bb269a80ca4241ec9f2d338817b05f1ff9d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831827"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>商務用 Skype Server 的使用者和用戶端驗證
 
受信任的使用者是指其認證已由商務用 Skype Server 中的受信任伺服器驗證的使用者。 在大部分的情況下，此伺服器可能是 Standard Edition Server、Enterprise Edition 前端伺服器或 Director。 商務用 Skype Server 依賴 Active Directory 網域服務做為使用者認證的單一、受信任的後端存放庫。
  
驗證是將使用者憑證佈建到受信任伺服器的歷程。 商務用 Skype Server 會根據使用者的狀態和位置，使用下列驗證通訊協定。
  
- **MIT Kerberos 5 安全性通訊協定**：用於具有 Active Directory 認證的內部使用者。Kerberos 需要用戶端連線至 Active Directory 網域服務，這也是為什麼它無法用來驗證企業防火牆外部的用戶端。
    
- **NTLM 通訊協定**：用於具有 Active Directory 認證，並且從企業防火牆外部端點連線的使用者。Access Edge Service 會將登入要求傳遞至 Director (如果存在) 或是前端伺服器進行驗證。Access Edge Service 本身不執行驗證工作。
    
    > [!NOTE]
    > NTLM 通訊協定所提供的攻擊防護較 Kerberos 弱，因此部分組織會盡量少用 NTLM。 因此，對商務用 Skype Server 的存取權可能會限制在內部或透過 VPN 或 DirectAccess 連線所連接的用戶端。 
  
- **摘要式通訊協定**：用於所謂的匿名使用者。匿名使用者是沒有認可的 Active Directory 認證，但受邀參加內部會議且擁有有效會議金鑰的外部使用者。摘要式驗證並非用以與其他用戶端互動。
    
商務用 Skype Server 驗證封裝含兩個階段：
  
1. 用戶端和伺服器之間會建立安全性關聯。
    
2. 用戶端和伺服器會使用現有的安全性關聯，簽署所傳送的訊息，並驗證接收的訊息。伺服器啟用驗證時，並不會接受來自用戶端的任何未驗證訊息。
    
使用者信任是附加於每個使用者發出的訊息中，而不是附加於使用者的識別證明上。伺服器會檢查每個訊息，看看是否具有有效的使用者憑證。如果使用者憑證有效，不但接收訊息的第一個伺服器不會驗證訊息，受信任伺服器 Cloud 中的所有伺服器也都不會驗證訊息。
  
具有同盟夥伴所發出之有效認證的使用者會受到信任，但是可能會選擇性地受到其他限制，而無法享有與內部使用者相同的完整權限。
  
ICE 和 TURN 通訊協定也會使用 IETF TURN RFC 中所述的摘要式挑戰。
  
用戶端憑證為使用者提供另一種商務用 Skype Server 驗證的方式。 使用者會具備解析密碼編譯挑戰所需之對應憑證的憑證和私密金鑰，而不是提供使用者名稱和密碼。  (此憑證必須具有識別使用者的主體名稱或主體替代名稱，且必須由執行商務用 Skype Server 之伺服器所信任的根 CA 所發出，請在憑證的有效期限內，且未被吊銷。 ) 若要進行驗證，使用者只需要輸入個人識別碼 (PIN) 。 憑證對電話、行動電話和其他裝置特別有用，因為這很難輸入使用者名稱和密碼。
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>由於 ASP .NET 4.5 的加密需求 

從商務用 Skype Server 2015 CU5 起，ASP.NET 4.6 不支援 AES，這可能會導致 Skype 會議應用程式無法啟動。 如果用戶端使用 AES 做為電腦金鑰驗證值，您必須將電腦金鑰值重設為 SHA-1，或 IIS 上 Skype 會議應用程式網站層級上其他支援的演算法。 如有必要，請參閱[IIS 8.0 ASP.NET 設定管理](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)以取得指示。
  
其他支援的值包括：
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  不允許使用 AES、3DES 和 MD5 值，就像在 ASP.NET 4 中那樣。 [ASP.NET 4.5，pt 中的加密增強功能](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)會有更多詳細資料。
