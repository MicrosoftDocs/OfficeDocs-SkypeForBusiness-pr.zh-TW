---
title: Lync Server 2013：建立或修改行動性原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a240c55b4478c5cf5f67a4f0774b1979e884b3b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改行動性原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以建立或修改行動性原則，讓行動使用者可以使用支援的行動裝置進行 Lync 功能（如立即訊息 (IM) 、目前狀態及連絡人）。 您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面建立或修改行動性原則

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server 控制台建立行動性原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **行動性原則** ] 導覽按鈕。

4.  在 [ **行動性原則** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
    1.  若要建立網站行動性原則，請依序按一下 [ **網站原則**]、網站、 **[確定]**、[檢查預設設定]，如果您想要，請進行任何變更。
    
    2.  若要建立使用者行動性原則，請依序按一下 [ **使用者原則**]、[名稱]、[複查預設設定] 及 [您要做任何變更]。

5.  按一下 **[認可]**。

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server 控制台修改行動性原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **行動性原則** ] 導覽按鈕。

4.  在 [ **行動性原則** ] 頁面上，按一下其中一個現有的行動性原則。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  編輯任何設定。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立外部存取原則

您可以使用 Windows PowerShell 和 **New-CsMobilityPolicy** Cmdlet，在網站範圍或個別使用者範圍) 中建立行動性原則 (。 此外，您也可以使用 **Set-CsMobilityPolicy** Cmdlet，修改任何現有的原則，包括全域原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>若要在網站範圍建立行動性原則

  - 此命令會為 Redmond 網站建立新的行動性原則：
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    由於上述命令中未指定任何 (必要 Identity 參數) 以外的參數，因此原則會將其所有屬性的預設值都使用。

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>在每個使用者範圍建立行動性原則

  - 若要在每個使用者範圍建立行動性原則，請指定原則的唯一身分識別：
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>在建立行動性原則時變更單一屬性值

  - 若要建立使用不同屬性值的原則，請加入適當的參數和參數值。 例如，此命令會建立行動原則，以停用通過工作的呼叫：
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>在建立行動性原則時變更多個屬性值

  - 多項屬性值可透過加入多個參數加以修改。 例如，此命令會建立同時停用行動及透過工作呼叫的原則：
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

如需詳細資訊，請參閱 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) 和 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定行動性原則](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

