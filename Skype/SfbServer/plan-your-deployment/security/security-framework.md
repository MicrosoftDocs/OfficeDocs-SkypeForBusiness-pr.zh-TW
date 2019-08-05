---
title: 商務用 Skype Server 的安全性架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本節概要說明構成商務用 Skype Server 安全架構的基本元素。 瞭解這些元素的運作方式, 對於保證您特定的商務用 Skype Server 部署的安全決策是必要的。
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192937"
---
# <a name="security-framework-for-skype-for-business-server"></a>商務用 Skype Server 的安全性架構
 
本節概要說明構成商務用 Skype Server 安全架構的基本元素。 瞭解這些元素的運作方式, 對於保證您特定的商務用 Skype Server 部署的安全決策是必要的。
  
這些元素如下所示:
  
- Active Directory 網域服務 (AD DS) 為使用者帳戶和網路資源提供單一受信任的後端儲備庫。
    
- 角色式存取控制 (RBAC) 可讓您委派管理工作, 同時維持高安全性的標準。
    
- 公開金鑰基礎結構 (PKI) 使用受信任的憑證授權單位 (Ca) 所頒發的憑證來驗證服務器並確保資料完整性。
    
- 傳輸層安全性 (TLS)、經由 SSL (HTTPS) 的 HTTPS 以及相互 TLS (MTLS) 啟用端點驗證與 IM 加密。 使用安全的即時傳輸通訊協定 (SRTP) 來加密點對點音訊、影片和應用程式共用資料流程。
    
- 使用者驗證的工業標準通訊協定 (如果可能)。
    
- Windows PowerShell 提供預設啟用的安全性功能, 讓使用者不會輕易或無意中執行腳本。
    
這些基本的安全性元素共同運作, 以定義受信任的使用者、伺服器、連線及作業, 以協助確保商務用 Skype Server 的安全基礎。
  
## <a name="in-this-section"></a>本節內容

本節中的主題描述這些基本元素的運作方式, 以增強商務用 Skype Server 基礎結構的安全性。
  
- [商務用 Skype Server 的 Active Directory 網域服務](active-directory-domain-services.md)
    
- [商務用 Skype Server 的以角色為基礎的存取控制 (RBAC)](role-based-access-control-rbac.md)
    
- [商務用 Skype Server 的公開金鑰基礎結構](public-key-infrastructure-for-skype.md)
    
- [商務用 Skype Server 的 TLS 和 MTLS](tls-and-mtls.md)
    
- [商務用 Skype Server 的加密](encryption.md)
    
- [商務用 Skype Server 的使用者和用戶端驗證](user-and-client-authentication.md)
    
- [Windows PowerShell 和商務用 Skype Server 管理工具](management-tools.md)
    

