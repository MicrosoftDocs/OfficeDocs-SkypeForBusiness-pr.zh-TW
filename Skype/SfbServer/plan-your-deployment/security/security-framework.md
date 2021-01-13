---
title: 商務用 Skype Server 的安全性架構
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
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本節概述構成商務用 Skype Server 安全性框架的基本元素。 瞭解這些元素的運作方式，對於在保護特定商務用 Skype Server 部署的相關決策方面是必要的。
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832093"
---
# <a name="security-framework-for-skype-for-business-server"></a>商務用 Skype Server 的安全性架構
 
本節概述構成商務用 Skype Server 安全性框架的基本元素。 瞭解這些元素的運作方式，對於在保護特定商務用 Skype Server 部署的相關決策方面是必要的。
  
這些元素如下：
  
- Active Directory 網域服務 (AD DS) 提供使用者帳戶和網路資源的單一信任後端存放庫。
    
- Role-Based 存取控制 (RBAC) 可讓您委派管理工作，同時維持高安全性標準。
    
- 公開金鑰基礎結構 (PKI) 會使用受信任的憑證授權單位單位 (CAs) 所發行的憑證，以驗證服務器並確保資料完整性。
    
- 傳輸層安全性 (TLS) 、HTTPS over SSL (HTTPS) ，以及相互 TLS (MTLS) 啟用端點驗證和 IM 加密。 使用安全 Real-Time 傳輸通訊協定 (SRTP) ，對點對點音訊、影片和應用程式共用資料流程進行加密。
    
- 適用于使用者驗證的業界標準通訊協定。
    
- Windows PowerShell 提供預設啟用的安全性功能，讓使用者無法輕易或無意中執行腳本。
    
這些基本的安全性元素共同運作，以定義信任的使用者、伺服器、連線和作業，以協助確保商務用 Skype Server 的安全基礎。
  
## <a name="in-this-section"></a>本節內容

本節中的主題說明這些基本元素的運作方式，以增強商務用 Skype 伺服器基礎結構的安全性。
  
- [商務用 Skype Server 的 Active Directory 網域服務](active-directory-domain-services.md)
    
- [商務用 Skype Server (RBAC) 角色的存取控制](role-based-access-control-rbac.md)
    
- [商務用 Skype Server 的公用機碼基礎結構](public-key-infrastructure-for-skype.md)
    
- [適用于商務用 Skype Server 的 TLS 及 MTLS](tls-and-mtls.md)
    
- [商務用 Skype Server 的加密](encryption.md)
    
- [商務用 Skype Server 的使用者和用戶端驗證](user-and-client-authentication.md)
    
- [Windows PowerShell 和商務用 Skype Server 管理工具](management-tools.md)
    

