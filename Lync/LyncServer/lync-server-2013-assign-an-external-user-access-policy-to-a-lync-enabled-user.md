---
title: Lync Server 2013：將外部使用者存取原則指派給擁有 Lync 功能的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 523907fbf4bc4cca93be8e529b6b607b43f0ea87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

如果使用者已啟用 Lync Server，您可以在 Lync Server 的 [控制台] 中設定 SIP 同盟、XMPP 同盟、遠端使用者存取及公用立即訊息（IM）連線，方法是將適當的原則套用至特定的使用者。 例如，如果您建立了支援遠端使用者存取的原則，您必須先將其套用至使用者，才能讓使用者從遠端位置連線到 Lync Server，並從遠端位置與內部使用者共同作業。

<div>


> [!NOTE]  
> 若要支援外部使用者存取，您必須針對您要支援的每個外部使用者存取類型啟用支援，然後設定適當的原則和其他選項來控制其用途。 如需詳細資訊，請參閱在 [部署檔] 中的 [在<A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013 中設定外部使用者存取支援</A>] 或 [在作業檔中<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">管理 lync server 2013 的同盟及外部存取</A>]。



</div>

使用本主題中的程式，將先前建立的外部使用者存取原則套用至一或多個使用者帳戶。

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>將外部使用者原則套用到使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [使用者]****，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

5.  在 [**外部存取原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的使用者原則。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用 [預設伺服器] 或 [全域原則設定]。

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派每個使用者的外部存取原則

您可以使用 Windows PowerShell 和 Grant CsExternalAccessPolicy Cmdlet 來指派每個使用者的外部存取原則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>將每個使用者的外部存取原則指派給單一使用者

  - 這個命令會將每個使用者的外部存取原則 RedmondExternalAccessPolicy 指派給使用者 Ken Myer。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>將每個使用者的外部存取原則指派給多個使用者

  - 這個命令會將每個使用者的外部存取原則 USAExternalAccessPolicy 指派給在 Active Directory 中的美國組織單位中擁有帳戶的所有使用者。 如需此命令中使用的 OU 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 的相關檔。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>若要取消指派每個使用者的外部存取原則

  - 這個命令會會先前指派給 Ken Myer 的任何每使用者外部存取原則。 未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。 網站原則的優先順序高於全域原則。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

如需詳細資訊，請參閱[Grant CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

