---
title: 驗證網域中的複寫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 若要驗證在步驟1： Prepare 架構中完成的網域準備作業，必須從商務用 Skype Server 管理命令介面 Lync Server 管理命令介面執行 Cmdlet。 若要執行 Windows PowerShell Cmdlet，請登入您準備好之網域成員的電腦，並以 domain Admins 群組成員的身分登入。 請執行下列動作：
ms.openlocfilehash: e02708e7b995c2f83e82080be60caa1e251f6b9438a75d93c7d74f47d812db93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319276"
---
# <a name="verify-replication-in-the-domain"></a>驗證網域中的複寫
 
若要驗證在 **步驟1： Prepare 架構** 中完成的網域準備作業，必須從商務用 Skype Server 管理命令介面 Lync Server 管理命令介面執行 Cmdlet。 若要執行 Windows PowerShell Cmdlet，請登入您準備好之網域成員的電腦，並以 domain Admins 群組成員的身分登入。 請執行下列動作：
  
1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 在 Windows PowerShell 中，輸入下列專案：
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    例如：
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > GlobalSettingsDomainController 參數可讓您指出全域設定的存放位置。 如果您的設定儲存在系統容器中 (（一般情況下，升級部署尚未將全域設定遷移至設定容器) ），您可以在 Active Directory 網域服務樹系的根目錄中定義網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您未指定此參數，Cmdlet 會假設設定儲存在設定容器中，並參照至 Active Directory 中的任何網域控制站。 
  
    如果您沒有指定 Domain 參數，這個值會設為本機網域。這個 Cmdlet 會在網域準備工作順利完成時，傳回值 **LC_DOMAIN_SETTINGS_STATE_READY**。
    

