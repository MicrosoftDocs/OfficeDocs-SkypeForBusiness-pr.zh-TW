---
title: Lync Server 2013：啟用或停用用戶端版本設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c575a861644c27a0dba93790667ece9b973211e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>啟用或停用 Lync Server 2013 中的用戶端版本設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

用戶端版本設定可用來開啟或關閉用戶端版本控制，不論是全域性或針對特定網站。 全域用戶端版本設定會以 Lync Server 2013 進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。 啟用全域設定時，任何已有的用戶端版本原則將會在使用者嘗試登入時生效。 如果您不想要進行任何用戶端版本控制，您可以停用全域用戶端版本設定。 您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，啟用或停用用戶端版本設定。

<div>


> [!NOTE]  
> 由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台啟用或停用用戶端版本設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本**設定] 導覽按鈕。

4.  執行下列動作：
    
      - 若要全域啟用或停用用戶端版本設定，請按兩下**全域**設定，然後修改設定。
    
      - 若要啟用或停用特定網站的用戶端版本設定，請依序按一下 [**新增**] 及 [網站]，然後按一下 **[確定]**，然後修改網站的設定。

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用用戶端版本設定

您可以使用**Set-CsClientVersionConfiguration** Cmdlet 來啟用或停用用戶端版本設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-client-versioning"></a>啟用用戶端版本設定

  - 您可以設定**Enabled**屬性為 True ($True) 來啟用用戶端版本設定。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>停用用戶端版本設定

  - 您可以將**Enabled**屬性設定為 False ($False) ，以停用用戶端版本設定。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

如需詳細資訊，請參閱[Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

