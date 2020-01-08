---
title: Lync Server 2013：確定撥號對應表具有指派的區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5aa91470accf0f25478b9233e1efb90357251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>確認 Lync Server 2013 已指派地區的撥號方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-02_

電話撥入式會議所用的撥號方案需要將電話撥**入**式會議區域指定為與適當的撥號方案關聯電話撥入式會議存取號碼。 當您設定撥號方案時，請指定適用于該撥號方案的電話撥入式會議區域。 接著，當您建立撥入存取號碼時，請選取將存取號碼與適當的撥號方案相關聯的地區。

由於對所有撥號方案指定區域很重要，因此建議您使用此程式來確認所有撥號方案都有地區。 此為選用步驟。

使用**CsDialPlan** Cmdlet 來驗證該區域是否已針對所有電話撥入式會議撥號方案進行設定。 如果撥號方案中的區域遺失，您可以使用**CsDialPlan** Cmdlet 來設定區域。 您也可以使用 Lync Server [控制台] 來更新現有撥號方案中的區域。 如需使用 Lync Server [控制台] 的詳細資料，請參閱[在 Lync server 2013 中修改撥號方案](lync-server-2013-modify-a-dial-plan.md)。

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>驗證撥號方案是否已設定 region 屬性

1.  以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元執行下列動作：
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    例如：
    
        Get-CsDialPlan
    
    在這個範例中，會傳回為貴組織設定的所有撥號計畫。

4.  查看傳回的撥號方案，以找出遺失電話撥入式會議區域的任何專案。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>若要設定撥號方案的 region 屬性

1.  以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  針對遺失電話撥入式會議區域的任何撥號方案，請執行：
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    例如：
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    在這個範例中，會修改具有雷德蒙者身分識別的撥號計畫，以將 DialinConferencingRegion 屬性設為 "US West Coast"。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

</div>

<span> </span>

</div>

</div>

</div>

