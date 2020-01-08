---
title: Lync Server 2013：將存檔原則套用至使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56bb6705187172888c9fdac33532e25a210e8246
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>將存檔原則套用至 Lync Server 2013 中的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

如果使用者已啟用 Lync Server 2013，而且您已經建立一或多個使用者原則，以供駐留在 Lync Server 2013 的使用者進行歸檔，您可以將適當的原則套用至這些使用者或使用者群組，以實現特定使用者的歸檔支援。 例如，如果您建立的原則支援內部通訊的歸檔，您可以將它套用至至少一個使用者或使用者群組，以支援使用者的 Lync Server 2013 通訊的封存。

<div>


> [!NOTE]  
> 如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。<BR>在啟用封存前，您應該先在封存配置中指定所有適當的選項。 如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">針對貴組織、網站和池管理 Lync Server 2013 中的 [封存配置選項</A>]。



</div>

使用本主題中的程式，將先前建立的存檔使用者原則套用至一或多個使用者帳戶或使用者群組。

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>將封存使用者原則套用到使用者帳戶

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]，然後搜尋您要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

5.  在 [**存檔原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的存檔使用者原則。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設伺服器安裝設定。 伺服器會自動套用這些設定。

    
    </div>

6.  按一下 [認可]****。

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派每個使用者的存檔原則

每個使用者的存檔原則都可以使用 Windows PowerShell 和**Grant CsArchivingPolicy** Cmdlet 來指派。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>將每個使用者的存檔原則指派給單一使用者

  - 下列命令會將每個使用者的存檔原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>將每個使用者的存檔原則指派給多個使用者

  - 這個命令會將每個使用者的存檔原則 RedmondArchivingPolicy 指派給擁有 [註冊機] 池 atl-cs-001.litwareinc.com 之帳戶的所有使用者。 如需此命令中使用之篩選參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 檔。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>指派每個使用者的存檔原則

  - 下列命令會以前指派給 Ken Myer 的任何每使用者封存原則。 未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。 網站原則的優先順序高於全域原則。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

如需詳細資訊，請參閱[Grant CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) Cmdlet 檔。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中管理內部和外部通訊的存檔](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[在 Lync Server 2013 中指派每個使用者的原則](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

