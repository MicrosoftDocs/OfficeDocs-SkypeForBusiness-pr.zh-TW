---
title: Lync Server 2013：建立或修改行動原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改行動原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以建立或修改行動原則，以允許行動使用者針對 Lync 功能（例如立即訊息（IM）、目前狀態及連絡人）使用支援的行動裝置。 您可以從 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 建立或修改行動原則

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>若要使用 Lync Server [控制台] 建立行動原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**行動原則**] 瀏覽按鈕。

4.  在 [**行動原則**] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：
    
    1.  若要建立網站行動原則，請按一下 [**網站原則**]，按一下網站，按一下 **[確定]**，查看預設設定，如果您想要的話，請進行任何變更。
    
    2.  若要建立使用者行動原則，請按一下 [**使用者原則**]，輸入名稱，查看預設設定，並視需要進行任何變更。

5.  按一下 [認可]****。

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server [控制台] 修改行動原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**行動原則**] 瀏覽按鈕。

4.  在 [**行動原則**] 頁面上，按一下其中一個現有行動原則。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  編輯任何設定。

7.  按一下 [認可]****。

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立外部存取原則

您可以使用 Windows PowerShell 和**新的 CsMobilityPolicy** Cmdlet，建立行動原則（在網站範圍或每個使用者範圍內）。 此外，您可以使用**CsMobilityPolicy** Cmdlet 來修改任何現有的原則，包括全域原則。 這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>在網站範圍建立行動原則

  - 這個命令會為雷德蒙網站建立新的行動原則：
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    因為在上述命令中沒有指定任何參數（除了強制身分識別參數以外），所以這些原則會針對其所有屬性使用預設值。

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>在每個使用者範圍建立行動原則

  - 若要在每個使用者範圍建立行動原則，請指定原則的唯一身分識別：
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>若要在建立行動原則時變更單一屬性值

  - 若要建立使用不同屬性值的原則，請包括適當的參數和參數值。 例如，這個命令會建立行動原則，透過工作停用通話：
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>若要在建立行動原則時變更多個屬性值

  - 您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會建立一個策略，透過工作停用行動與通話：
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

如需詳細資訊，請參閱[新的 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)和[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定行動原則](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

