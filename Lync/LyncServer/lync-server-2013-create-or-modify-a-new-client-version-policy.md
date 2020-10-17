---
title: Lync Server 2013：建立或修改新的用戶端版本原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb78150097fe7bde3b72338b3d1c9c37dc2a9b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506110"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改新的用戶端版本原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以使用用戶端版本原則，指定環境中支援的用戶端版本。 使用用戶端版本設定可協助減少支援多個用戶端版本相關的成本。 它也可以改善整體使用者經驗，因為當舊版用戶端與更新版本互動時，舊版的用戶端就可以限制可用的功能。 您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，建立或修改用戶端版本原則。

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台建立或修改用戶端版本原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]。
    
    <div>
    

    > [!NOTE]  
    > 預設會選取 [ <STRONG>用戶端版本原則</STRONG> ] 索引標籤。

    
    </div>

4.  在 [ **用戶端版本原則** ] 頁面上，執行下列其中一項操作：
    
      - 若要建立用戶端版本原則，請按一下 [ **新增**]，選取 [ **網站原則**]、[ **集區原則**] 或 [ **使用者原則**]，然後按一下 **[確定]**。
    
      - 若要修改全域原則或其他現有的用戶端版本原則，請選取原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯用戶端版本原則** ] 頁面上，如在 [Lync Server 2013 中建立或修改新的用戶端版本原則規則](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)中所述，建立或修改規則。

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立或修改用戶端版本原則

您可以使用 **New-CsClientVersionPolicy** Cmdlet 來建立用戶端版本原則，並使用 **Set-CsClientVersionPolicy** Cmdlet 加以修改。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>若要建立新的網站範圍用戶端版本原則

  - 下列命令會建立套用至 Redmond 網站的新用戶端版本原則。 由於未指定其他參數，因此新原則會使用預設的用戶端版本設定。
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>若要建立新的每一使用者用戶端版本原則

  - 若要建立每一使用者原則，請使用類似下列的命令：
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

如需詳細資訊，請參閱 [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet 及 [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

