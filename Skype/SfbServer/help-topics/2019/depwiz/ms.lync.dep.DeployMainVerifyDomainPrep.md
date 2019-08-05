---
title: 驗證網域中的複寫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: '若要驗證在步驟 1: 準備架構中完成的網域準備, 必須從商務用 Skype Server Management Shell Lync Server 管理命令介面執行 Cmdlet。 若要執行 Windows PowerShell Cmdlet, 請登入您已準備之網域成員的電腦, 以及作為網域管理員群組的成員。 請執行下列步驟：'
ms.openlocfilehash: 0b853a071116525ad313cf351685124bf92782a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193518"
---
# <a name="verify-replication-in-the-domain"></a>驗證網域中的複寫
 
若要驗證在**步驟 1: 準備架構**中完成的網域準備, 必須從商務用 Skype Server Management Shell Lync Server 管理命令介面執行 Cmdlet。 若要執行 Windows PowerShell Cmdlet, 請登入您已準備之網域成員的電腦, 以及作為網域管理員群組的成員。 請執行下列步驟：
  
1. 啟動商務用 Skype Server 管理命令介面: 請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**], 然後按一下 [**商務用 skype server 管理命令**介面]。
    
2. 在 Windows PowerShell 中, 輸入下列內容:
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    例如：
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > GlobalSettingsDomainController 參數可讓您指出全域設定的存放位置。 如果您的設定是儲存在系統容器中 (這通常是使用未將全域設定遷移至配置容器的升級部署), 您可以在 Active Directory 網域服務林的根目錄中定義網網域控制站。 如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。 如果您沒有指定此參數, Cmdlet 會假設設定會儲存在配置容器中, 並參照 Active Directory 中的任何網網域控制站。 
  
    如果您沒有指定 Domain 參數，則會將此值設定至本機網域。 這個 Cmdlet 會在網域準備工作完成時，傳回 **LC_DOMAIN_SETTINGS_STATE_READY** 值。
    

