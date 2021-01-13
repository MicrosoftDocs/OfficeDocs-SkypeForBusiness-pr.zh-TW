---
title: 建立商務用 Skype Server 控制台管理員
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 若要授與商務用 Skype Server 2015 的存取權，請執行下列操作：
ms.openlocfilehash: 40c119f99182dc2416a1414db2a2fc143e818352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811073"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>建立商務用 Skype Server 控制台管理員
 
若要授與商務用 Skype Server 2015 的存取權，請執行下列操作：
  
1. 使用 Domain Admins 群組成員或 RTCUniversalServerAdmins 群組成員的身分登入。
    
2. 開啟 **[Active Directory 使用者和電腦]**，展開網域，以滑鼠右鍵按一下 **[使用者]** 容器，然後按一下 **[內容]**。
    
3. 在 [CSAdministrator 內容] 中，按一下 [成員] 索引標籤。
    
4. 在 [成員] 索引標籤上，按一下 [新增]。在 [選取使用者、連絡人、電腦、服務帳戶或群組] 中，找到 [輸入要選取的物件名稱]。輸入要新增到 CSAdministrators 群組的使用者名稱或群組名稱。按一下 [確定]。
    
5. 在 [成員] 索引標籤上，確認您選取的使用者或群組已存在。按一下 [確定]。
    
> [!TIP]
> 商務用 Skype Server 控制台是以角色為基礎的存取控制工具。 CsAdministrator 群組中的成員資格會為所有可用的設定功能提供使用商務用 Skype Server 控制台完全控制權的使用者。 有些其他的角色是針對特定功能而設計。 使用者並非必須啟用商務用 Skype 伺服器才能成為管理群組的成員。 
  
其他角色包括：
  
- **CsArchiving：** 此群組的成員可以執行所有封存功能，例如設定和管理封存伺服器角色。
    
- **CsHelpDesk：** 這個群組的成員可以檢視設定和部署，包括使用者內容及原則。成員也可以執行特定的疑難排解工作。
    
- **CsLocationAdministrator：** 成員具有與增強型 9-1-1 (E9-1-1) 管理相關聯的最低層級使用者權利。他們可以建立 E9-1-1 位置及網路識別碼，並在部署中建立其關聯。
    
- **CsResponseGroupAdministrator：** 成員可以管理和設定回應群組服務。
    
- **CsServerAdministrator：** 成員可以管理、監控及疑難排解所有執行商務用 Skype 伺服器的伺服器。
    
- **CsUserAdministrator：** 成員可以管理、啟用與停用使用者，以及指派現有的原則給使用者。
    
- **CsViewOnlyAdministrator：** 成員可以查看伺服器資訊的部署和設定。 此成員資格可讓成員監視執行商務用 Skype Server 2015 之伺服器的健康情況。
    
- **CsVoiceAdministrator：** 成員可以在商務用 Skype Server 中建立、設定及管理語音相關的設定。
    
若要協助保留安全性和角色型存取控制完整性，請將使用者新增至定義使用者在管理商務用 Skype Server 部署時所執行之角色的群組。
  

