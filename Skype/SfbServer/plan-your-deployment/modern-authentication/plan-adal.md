---
title: '使用商務用 Skype 規劃新式驗證 (ADAL) '
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 本文說明使用 Active Directory 驗證程式庫 (ADAL) 和 OAuth 2.0) 的新式驗證 (。
ms.openlocfilehash: 40bf87317b68e258fc6576b1ce7be7b8decc6939
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834079"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>如何搭配商務用 Skype 使用新式驗證 (ADAL) 
 
本文介紹新式驗證 (，這是根據 Active Directory 驗證程式庫 (ADAL) 和 OAuth 2.0) ，可在商務用 Skype 的 3 2016 月累積更新中找到商務用 Skype Server 2015，或最初版本為商務用 Skype Server 2019。
  
## <a name="what-is-adal"></a>什麼是 ADAL？

ADAL 是「Active Directory 驗證程式庫」的縮寫，以及 OAuth 2.0，是新式驗證的基礎。 此程式碼庫的設計目的是讓用戶端應用程式可以使用目錄中的安全資源 (例如商務用 Skype) 透過安全性權杖。 ADAL 可與 OAuth 2.0 搭配使用，以啟用更多驗證和授權案例，例如多重要素驗證 (MFA) 和其他形式的 SAML Auth。
  
可充當用戶端的各種應用程式可利用新式驗證取得安全資源的協助。 在商務用 Skype Server 中，此技術是用於內部部署用戶端和內部部署伺服器之間，以便為使用者提供適當的資源授權層級。
  
新式驗證交談 (以 ADAL 和 OAuth 2.0 為基礎) 具有一些共同元素。
  
- 有用戶端要求資源，在此情況下，用戶端為商務用 Skype。
    
- 有一個資源可供用戶端需要特定的存取層級，而且此資源由目錄服務保護，在此情況下，資源商務用 Skype Server。
    
- 有 OAuth 連線，也就是說，專門用來  *授權*  使用者存取資源的連線。  (OAuth 也是更具描述性的名稱「Server-to-Server ' 驗證，而且通常是 S2S 的縮寫。 ) 
    
在商務用 Skype Server 新式驗證 (ADAL) 交談，商務用 Skype Server 會透過 adfs (Windows Server 2012 R2) 中的 adfs 3.0 進行通訊。 驗證可能會使用其他一些身分識別提供者 (IdP) ，但商務用 Skype 伺服器必須設定為與 ADFS 直接通訊。 若尚未設定 ADFS 使用商務用 Skype Server 請完成[ADFS 安裝](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。
  
ADAL 會包含在商務用 Skype Server 2015 的三月份2016累積更新中，而且必須安裝商務用 Skype 的2016三月份累積更新，且 **必須** 安裝，才能成功設定。 若為商務用 Skype Server 2019，可從產品的初始版本取得。
  
> [!NOTE]
> 在初次發行時，只有在沒有任何混合的 Skype 拓撲的情況下，才支援內部部署環境中的新式驗證。 例如，如果環境純粹商務用 Skype Server。 此語句可能會變更。 
  
包含具有 ADAL 使用之命令的 PowerShell .ps1 套件，必須下載該檔才能成功設定。

如需如何在商務用 Skype 中執行新式驗證的詳細資訊，請參閱：[如何使用新式驗證 (ADAL) 搭配商務用 Skype](/microsoft-365/enterprise/hybrid-modern-auth-overview)