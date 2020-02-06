---
title: 使用商務用 Skype 規劃新式驗證（ADAL）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文說明什麼是現代驗證（以 Active Directory 驗證庫（ADAL）和 OAuth 2.0）為基礎。
ms.openlocfilehash: 239dd6a49ecbec043a661e622a66eb5cb4665e96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815831"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何在商務用 Skype 中使用新式驗證（ADAL）
 
本文將介紹現代驗證（這是以 Active Directory 驗證庫（ADAL）和 OAuth 2.0）為基礎的，可在商務用 skype Server 2015 的商務用 Skype 的2016年3月累計更新中找到，或從初始商務用 Skype Server 2019 的發行。
  
## <a name="what-is-adal"></a>什麼是 ADAL？

ADAL 是「Active Directory 驗證文件庫」的縮寫，以及 OAuth 2.0，是新式驗證的基礎。 這個程式碼庫的設計目的是為了讓您目錄中的安全資源可供用戶端應用程式（例如商務用 Skype）透過安全權杖使用。 ADAL 可與 OAuth 2.0 搭配使用，以啟用更多驗證與授權案例，例如多重要素驗證（MFA），以及其他形式的 SAML 身分驗證。
  
充當用戶端的各種應用程式都可以利用新式驗證來取得安全資源的協助。 在商務用 Skype Server 中，此技術是在內部部署用戶端與內部部署伺服器之間使用，以便為使用者提供適當的資源授權層級。
  
新式驗證交談（以 ADAL 和 OAuth 2.0 為基礎）有一些常見的元素。
  
- 用戶端提出資源要求，在此案例中，用戶端是商務用 Skype。
    
- 用戶端需要特定的存取層級，而這個資源是由目錄服務來保護，在此案例中，資源是商務用 Skype Server。
    
- 有一個 OAuth 連線，也就是一個專用來*授權*使用者存取資源的連線。 （OAuth 也是由更具描述性的名稱 [伺服器到伺服器] 驗證，通常縮寫為 S2S）。
    
在商務用 Skype Server 新式驗證（ADAL）交談中，商務用 Skype 伺服器是透過 ADFS （在 Windows Server 2012 R2 中的 ADFS 3.0）進行通訊。 驗證可能會使用一些其他身分識別提供者（IdP）進行，但商務用 Skype 伺服器必須設定為與 ADFS 直接通訊。 如果您尚未將 ADFS 設定為與商務用 Skype 伺服器搭配使用，請完成[ADFS 安裝](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。
  
在商務用 Skype Server 2015 的2016年3月累計更新中，且**必須**安裝適用于商務用 skype 的年 3 2016 月累計更新，才能成功進行設定。 如果是商務用 Skype Server 2019，就可以從產品初次發行中取得。
  
> [!NOTE]
> 在初始發行期間，只有在沒有任何混合 Skype 拓撲涉及的情況下，才支援內部部署環境中的新式驗證。 例如，如果環境是純粹的商務用 Skype 伺服器。 此語句可能受變更。 
  
您必須下載包含在 ADAL 中使用之命令的 PowerShell 套件（包括 ps1 檔案），才能成功進行設定。

如需如何在商務用 Skype 中實施新式驗證的詳細資訊，請參閱：[如何在商務用 skype 中使用新式驗證（ADAL）](../../manage/authentication/use-adal.md)
