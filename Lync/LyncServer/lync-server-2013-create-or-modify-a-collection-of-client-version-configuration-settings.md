---
title: 建立或修改用戶端版本設定的集合
description: 建立或修改用戶端版本設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0082b618b8417c9d0da44599f1606cd238dfd7e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578309"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改用戶端版本設定的集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會與 Lync Server 一起安裝，用來啟用或停用整個伺服器部署的用戶端版本控制。 您也可以設定個別網站的用戶端版本設定。 您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，建立或修改用戶端版本設定。

<div>


> [!NOTE]
> 由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台建立或修改用戶端版本設定設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **用戶端版本** 設定] 導覽按鈕。

4.  在 [ **用戶端版本** 設定] 頁面上，執行下列動作：
    
      - 若要建立新的設定，請依序按一下 [ **新增**] 及 [網站]，然後按一下 **[確定名稱]** 並更新設定。
    
      - 若要修改設定，請選取設定，按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]，然後對設定進行變更。

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立或修改用戶端版本設定設定

您可以使用 **set-csclientversionconfiguration** Cmdlet 來建立用戶端版本設定設定，並使用 **Set-CsClientVersionConfiguration** Cmdlet 進行修改。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>若要建立新的用戶端版本設定的集合

  - 下列命令會建立套用至 Redmond 網站的新用戶端版本設定的集合。 在此範例中，會停用 Redmond 網站的用戶端版本設定。
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>啟用網站的用戶端版本設定

  - 此命令可啟用 Redmond 網站的用戶端版本設定。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>停用整個組織中的用戶端版本設定

  - 在此範例中，組織中使用的所有用戶端版本設定均會停用用戶端版本設定。
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

如需詳細資訊，請參閱 [set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) 和 [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

