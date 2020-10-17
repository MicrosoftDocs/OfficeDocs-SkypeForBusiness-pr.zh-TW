---
title: Lync Server 2013：將外部使用者存取原則指派給啟用 Lync 功能的使用者
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
ms.openlocfilehash: 7d7b1f9436695c5bd455c376d9c75add996be28f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508940"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>在 Lync Server 2013 中將外部使用者存取原則指派給啟用 Lync 功能的使用者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

如果使用者已啟用 Lync Server，您可以將適當的原則套用至特定使用者，以在 Lync Server 控制台中設定 SIP 同盟、XMPP 同盟、遠端使用者存取和公用立即訊息 (IM) 連線。 例如，如果您建立原則來支援遠端使用者存取，則必須先將其套用至使用者，使用者才能從遠端位置連接至 Lync Server，並從遠端位置與內部使用者共同作業。

<div>


> [!NOTE]  
> 若要支援外部使用者存取，您必須啟用想要支援之每種外部使用者存取類型的支援，以及設定適當原則及其他控制使用的選項。 如需詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-support-for-external-user-access.md">外部使用者2013存取的支援</A> ，或管理 Operations 檔中的 <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">lync server 2013 的同盟與外部存取</A> 。



</div>

使用本主題中的程序，將先前建立的外部使用者存取原則套用至一或多個使用者帳戶。

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>將外部使用者原則套用至使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在 **[外部存取原則]** 的 **[編輯 Lync Server 使用者]** 下，選取想要套用的使用者原則。
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設伺服器或全域原則設定。

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 外部存取原則

您可以使用 Windows PowerShell 和 Grant-CsExternalAccessPolicy Cmdlet 指派每個使用者的外部存取原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>將個別使用者外部存取原則指派給單一使用者

  - 此命令可將個別使用者外部存取原則 RedmondExternalAccessPolicy 指派給使用者 Ken Myer。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>將個別使用者外部存取原則指派給多個使用者

  - 此命令可將個別使用者外部存取原則 USAExternalAccessPolicy，指派給所有具有 Active Directory 中之 UnitedStates OUto 帳戶的使用者。 如需此命令中所使用之 OU 參數的詳細資訊，請參閱 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 的檔。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>取消指派個別使用者外部存取原則

  - 此命令可將任何先前指派給 Ken Myer 的個別使用者外部存取原則予以解除指派。一旦解除指派個別使用者原則，即會自動使用全域原則或其本機網站原則 (如果存在的話) 來管理 Ken Myer。網站原則的優先順序高於全域原則。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

如需詳細資訊，請參閱 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

