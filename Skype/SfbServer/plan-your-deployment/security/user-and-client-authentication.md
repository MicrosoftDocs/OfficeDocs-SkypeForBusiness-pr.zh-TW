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
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>商務用 Skype Server 的使用者和用戶端驗證
 
受信任的使用者是認證已由商務用 Skype Server 中的受信任伺服器進行驗證的人。 此伺服器通常是標準版 server、Enterprise Edition 前端伺服器或控制器。 商務用 Skype Server 依賴 Active Directory 網域服務做為使用者認證的單一、受信任後端儲存庫。
  
驗證是將使用者認證提供給信任的伺服器。 商務用 Skype 伺服器會根據使用者的狀態和位置, 使用下列驗證通訊協定。
  
- 針對具有 Active Directory 認證的內部使用者, **MIT Kerberos 版本5安全通訊協定**。 Kerberos 需要用戶端連線至 Active Directory 網域服務, 這就是為什麼它無法用來驗證公司防火牆外部的用戶端。
    
- 適用于使用者的**NTLM 通訊協定**, 其 Active Directory 認證是從公司防火牆以外的端點連線。 [存取邊緣服務] 會將登入要求傳到主管 (如果有的話), 或傳遞給前端伺服器進行驗證。 存取邊緣服務本身不會執行任何驗證。
    
    > [!NOTE]
    > NTLM 通訊協定提供的防護防護功能不夠安全, 因此有些組織會將 NTLM 的使用量降至最低。 因此, 存取商務用 Skype 伺服器的方式可能會限制為內部或透過 VPN 或 DirectAccess 連線進行連線的用戶端。 
  
- 稱為匿名使用者的**摘要通訊協定**。 匿名使用者是指沒有辨識 Active Directory 認證但受邀者加入內部部署會議, 且擁有有效會議金鑰的使用者。 [摘要式驗證] 不用於其他用戶端互動。
    
商務用 Skype 伺服器驗證是由兩個階段組成:
  
1. 在用戶端與伺服器之間建立安全關聯。
    
2. 用戶端和伺服器使用現有的安全性關聯來簽署其傳送的訊息, 並驗證收到的訊息。 在伺服器上啟用驗證時, 不會接受來自用戶端的未驗證訊息。
    
使用者信任已附加至源于使用者的每一封郵件, 而不是使用者身分識別本身。 伺服器會檢查每一封郵件是否有有效的使用者認證。 如果使用者認證有效, 則除了由第一個伺服器來接收郵件, 但在受信任的伺服器雲端中, 所有其他伺服器, 都不會 unchallenged 該郵件。
  
具有聯盟夥伴所頒發之有效認證的使用者是受信任的, 但其他限制式可讓您享受完整的許可權 accorded 給內部使用者。
  
[ICE] 和 [轉換] 通訊協定也會使用 [摘要式轉換 RFC] 中所述的摘要問題。
  
用戶端憑證為使用者提供由商務用 Skype 伺服器驗證的替代方法。 使用者不會提供使用者名稱和密碼, 而是會有一個憑證和私密金鑰對應至解決密碼質詢所需的憑證。 (此憑證必須有識別使用者且必須由執行商務用 Skype Server 的伺服器所信任之根 CA 所頒發, 請在證書的有效期內, 且未被吊銷。)若要進行驗證, 使用者只需要輸入個人識別碼 (PIN)。 憑證對於電話、行動電話及其他難以輸入使用者名稱和密碼的裝置非常有用。
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>ASP .NET 4.5 的加密需求 

從商務用 Skype Server 2015 CU5, 不支援 ASP.NET 4.6 的 AES, 這可能會導致 Skype 會議應用程式無法啟動。 如果用戶端使用的是 AES 作為電腦金鑰驗證值, 您將需要在 IIS 上的 Skype 會議應用程式網站層級將電腦金鑰值重設為 SHA-1 或其他支援的演算法。 如有需要, 請參閱[IIS 8.0 ASP.NET 設定管理](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)以取得相關指示。
  
其他支援的值為:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  我們不再允許使用值 AES、3DES 和 MD5, 就像在 ASP.NET 4 中一樣。 [ASP.NET 4.5, pt 中的密碼增強功能](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)有更多詳細資料。
  
