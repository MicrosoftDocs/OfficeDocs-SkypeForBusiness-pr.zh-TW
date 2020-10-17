---
title: Lync Server 2013：將封存原則套用至使用者
description: Lync Server 2013：將封存原則套用至使用者。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b82a68a75da7b389167097d8b08358cf680e1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544969"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>將封存原則套用至 Lync Server 2013 中的使用者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

如果使用者已啟用 Lync Server 2013，且已建立一或多個使用者原則來封存位於 Lync Server 2013 的使用者，您可以將適當的原則套用至那些使用者或使用者群組，以對特定使用者執行封存支援。 例如，如果您建立支援內部通訊封存的原則，您可以將它套用至至少一個使用者或使用者群組，以支援使用者的 Lync Server 2013 通訊的封存。

<div>


> [!NOTE]  
> 如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。<BR>啟用封存前，應在封存組態中指定所有適當的選項。 如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">管理組織、網站及集區的 Lync Server 2013 中的封存配置選項</A> 。



</div>

使用本主題中的程序，將先前建立的封存使用者原則套用至一或多個使用者帳戶或使用者群組。

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>將封存使用者原則套用至使用者帳戶

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在 [封存**原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的封存使用者原則。
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt; 自動 &gt; </STRONG>設定會套用預設伺服器安裝設定。 伺服器會自動套用這些設定。

    
    </div>

6.  按一下 **[認可]**。

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 封存原則

您可以使用 Windows PowerShell 和 **Grant-CsArchivingPolicy** Cmdlet 指派每個使用者的封存原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>將每一使用者封存原則指派給單一使用者

  - 下列命令將個別使用者封存原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>將每一使用者封存原則指派給多個使用者

  - 此命令將個別使用者封存原則 RedmondArchivingPolicy 指派給帳戶位於登錄器集區 atl-cs-001.litwareinc.com 的所有使用者。 如需此命令中使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet 檔。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>指派每位使用者的封存原則

  - 下列命令解除指派任何先前指派給 Ken Myer 的個別使用者封存原則。一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。網站原則優先順序高於全域原則。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

如需詳細資訊，請參閱 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) Cmdlet 檔。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中管理內部和外部通訊的封存](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[在 Lync Server 2013 中指派每一使用者原則](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

