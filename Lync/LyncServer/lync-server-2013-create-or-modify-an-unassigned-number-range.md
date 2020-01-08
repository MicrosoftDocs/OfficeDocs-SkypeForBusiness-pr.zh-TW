---
title: Lync Server 2013：建立或修改未指定的數位範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88c24e1f76e6c07e1a5e32b075aec6aa7de23ea1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改未指定的數位範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用下列其中一個程式來設定宣告應用程式的未指派數量範圍。

<div>


> [!IMPORTANT]  
> 在您設定 [未指派的號碼] 資料表之前，您必須已定義一或多個宣告，或設定 Exchange 整合通訊（UM）自動語音應答。



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>使用 Lync Server [控制台] 設定未指派的電話號碼

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音功能**]，然後按一下 [**未指定的號碼**]。

4.  在 [**未指定的號碼**] 頁面上，執行下列其中一項操作：
    
      - 若要建立新的編號範圍，請按一下 [**新增**]。 在 [**名稱**] 中，輸入此數位範圍的識別名稱。
        
        <div>
        

        > [!NOTE]  
        > 在您將新的未指派的數位範圍提交至資料庫之後，您就無法變更此名稱。

        
        </div>
    
      - 若要修改現有的數位範圍，請在 [搜尋] 欄位中輸入全部或部分的數位範圍名稱。 在產生的數位範圍清單中，按一下您想要的名稱，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在第一個 [**數位範圍**] 欄位中，輸入範圍的起始編號，然後在 [第二個**數位範圍**] 欄位中，輸入範圍的結束數位。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>該範圍的起始號碼必須小於或等於範圍的結束號碼。</P>
    > <LI>
    > <P>如果範圍的起始編號或範圍的結束數位包含分機號碼，則起始編號與範圍的結束數位都必須包含延伸，且起始編號和所需的延伸號碼必須是相同的。結束數位。</P>
    > <LI>
    > <P>這個數位必須符合正則運算式（電話：）嗎？（\+)?[1-9] \d{0,17}（; ext = [1-9] \d{0,9}）？。 這表示數位可能會從電話號碼開始：（如果您沒有指定該字串，會自動為您新增）、加號（+），以及1到9的數位。 電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。</P></LI></UL>

    
    </div>

6.  在 [**宣告服務**] 中，執行下列其中一項操作：
    
      - 按一下 [**宣告**]。
    
      - 按一下 [ **EXCHANGE UM**]。

7.  如果您在上一個步驟中按一下 [**宣告**]，請執行下列動作：
    
    1.  在 [**目的地伺服器的 FQDN**] 底下，按一下 [**選取**]，然後按一下執行宣告應用程式的應用程式服務識別碼，該應用程式服務會處理撥入呼叫到此未指定號碼的範圍，然後按一下 **[確定]**。
    
    2.  在 [**宣告**] 中，按一下要在此未指定編號範圍中播放的宣告。

8.  如果您在上一個步驟中按一下 [ **EXCHANGE UM**]，請在 [**自動語音應答電話號碼**] 底下，按一下 [**選取**]，然後按一下要用於此未指定號碼範圍的電話號碼，然後按一下 **[確定]**。

9.  按一下 [確定]****。

10. 在 [**未指定的號碼**] 頁面上，確定未指定的數位範圍是依您想要的順序排列。 若要變更範圍在表格中的位置，請在範圍清單中按一下一或多個連續的名稱，然後按一下向上箭號或向下箭號。
    
    <div>
    

    > [!TIP]  
    > Lync Server 會從上到下搜尋 [未指定的數位] 資料表，並使用符合未指定數位的第一個範圍。 如果您有重迭的範圍，且一個範圍指定了 [最後一個滑雪場] 動作，請確定該範圍位於清單底部。

    
    </div>

11. 當您以您想要的順序排列 [未指定的數位範圍] 時，請按一下 [**全部確認**]。

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>使用 Windows PowerShell 來設定未指派的電話號碼

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  使用 [**新-CsUnassignedNumber** ] 來建立新的 [未指定的數位範圍]。 使用 [**設定] CsUnassignedNumber**來修改現有的未指派數位範圍。
    
    <div>
    

    > [!TIP]  
    > 如果您有重迭的範圍，且想要以特定順序套用範圍，請包含 Priority 參數。 具有最高優先順序的範圍會套用至通話。

    
    </div>
    
    在命令列上，執行下列其中一項操作：
    
      - 若要為宣告服務建立數位範圍，請執行：
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - 或者，若要建立 Exchange UM 自動語音應答的數位範圍，請執行：
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    例如：
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    或
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    下列範例顯示如何修改現有未指定的數位範圍中的數位：
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中刪除未指定的數位範圍](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

