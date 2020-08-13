---
title: Lync Server 2013：建立或修改未指派號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7252b2cda2f957dc72e006b7ce298bc5dd87fd5a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改未指派號碼範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用下列其中一個程式來設定宣告應用程式的未指派號碼範圍。

<div>


> [!IMPORTANT]  
> 在您設定未指派的號碼表之前，您必須已定義一或多個宣告或設定 Exchange 整合通訊 (UM) 自動語音應答。



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>使用 Lync Server 控制台設定未指派的電話號碼

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 [**語音功能**] 和 [**未指派的號碼**]。

4.  在 [**未指派的號碼**] 頁面上，執行下列其中一項操作：
    
      - 若要建立新的號碼範圍，請按一下 [**新增**]。 在 **[名稱]** 中，輸入此號碼範圍的識別名稱。
        
        <div>
        

        > [!NOTE]  
        > 在您認可新的未指派號碼範圍至資料庫之後，就無法變更此名稱。

        
        </div>
    
      - 若要修改現有的號碼範圍，請在 [搜尋] 欄位中輸入編號範圍的全部或部分名稱。 在產生的號碼範圍清單中，按一下您想要的名稱，然後按一下 [**編輯**]，再按一下 [**顯示詳細資料**]。

5.  在第一個 **[號碼範圍]** 欄位中輸入範圍的開始號碼，在第二個 **[號碼範圍]** 欄位中輸入範圍的結束號碼。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>該範圍的起始號碼必須小於或等於範圍的結束號碼。</P>
    > <LI>
    > <P>如果範圍的開始號碼或範圍的結束號碼包含分機號碼，則範圍的開始號碼和結束號碼都必須包含分機，且開始號碼和結束號碼的分機號碼必須相同。</P>
    > <LI>
    > <P>號碼必須符合正則運算式 (電話： ) ？ (\+) ？ [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ？。 這表示數位可以從電話號碼開始： (若您未指定該字串，就會自動為您新增) 、加號 (+) 及數位1到9。 電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。</P></LI></UL>

    
    </div>

6.  在 **[宣告服務]** 中，執行下列其中一個動作：
    
      - 按一下 **[宣告]**。
    
      - 按一下 **[Exchange UM]**。

7.  如果您在上一個步驟按了 **[宣告]**，請執行下列動作：
    
    1.  在 **[目的地伺服器的 FQDN]** 下方按一下 **[選取]**，按一下執行宣告應用程式之應用程式服務的服務 ID (此服務會處理此未指派號碼範圍的來電)，然後按一下 **[確定]**。
    
    2.  在 **[宣告]** 中，按一下要針對此未指派號碼範圍播放的宣告。

8.  如果您在上一個步驟按了 **[Exchange UM]**，請在 **[自動語音應答電話號碼]** 下方按一下 **[選取]**，按一下要用於此未指派號碼範圍的電話號碼，然後按一下 **[確定]**。

9.  按一下 **[確定]**。

10. 在 [**未指派的號碼**] 頁面上，確定未指派的號碼範圍以您想要的順序排列。 若要變更某個範圍在表格中的位置，請在範圍清單中按一下一個或多個連續的名稱，然後按一下向上鍵或向下箭號。
    
    <div>
    

    > [!TIP]  
    > Lync Server 會從上到下搜尋未指派號碼表格，並使用符合未指派號碼的第一個範圍。 如果您有重疊的範圍，且有一個範圍指定最後採取的動作，請確定該範圍位於清單底部。

    
    </div>

11. 當您以您想要的順序排列未指派的號碼範圍時，請按一下 [**全部認可**]。

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>使用 Windows PowerShell 設定未指派的電話號碼

1.  以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用**New-CsUnassignedNumber**建立新的未指派號碼範圍。 使用**Set-CsUnassignedNumber**修改現有的未指派號碼範圍。
    
    <div>
    

    > [!TIP]  
    > 如果您有重疊的範圍，且想要依特定順序套用範圍，請包含 Priority 參數。 具有最高優先順序的範圍會套用至通話。

    
    </div>
    
    在命令列中，執行下列其中一項操作：
    
      - 若要建立宣告服務的號碼範圍，請執行：
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - 或者，若要建立 Exchange UM 自動語音應答的號碼範圍，請執行：
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    例如：
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    或
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    下列範例會顯示如何修改現有未指派號碼範圍中的號碼：
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除未指派的號碼範圍](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

