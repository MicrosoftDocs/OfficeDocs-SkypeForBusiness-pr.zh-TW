---
title: Lync Server 2013：查看用戶端版本原則規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4bf9d60d9f99addffed25a87b05ea91650294
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>在 Lync Server 2013 中查看用戶端版本原則規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

用戶端版本原則是由一組用戶端版本原則規則所組成。 當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。 您可以從 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 查看用戶端版本原則規則。

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 來查看用戶端版本原則規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本原則**] 瀏覽按鈕。

4.  在 [**用戶端版本原則**] 頁面上，按兩下您要查看的用戶端版本原則。

5.  這些規則會出現在 [**編輯用戶端版本原則**] 頁面上。 若要查看規則的詳細資料，請選取規則，然後按一下 [**顯示詳細資料**]。

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看用戶端版本原則規則

您可以使用 Lync Server 管理命令介面和**CsClientVersionPolicyRule** Cmdlet 來查看用戶端版本原則規則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-client-version-policy-rules"></a>若要查看用戶端版本原則規則

  - 若要查看用戶端版本原則規則，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsClientVersionPolicyRule
    
    這會針對每個設定的規則傳回如下所示的資訊：
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

如需詳細資訊，請參閱[CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

