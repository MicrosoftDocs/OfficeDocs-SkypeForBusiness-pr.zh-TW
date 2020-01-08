---
title: (選用) 啟用和停用會議加入和離開宣告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 778969dfa5ed6b84fdbcd2b204e497f8d649f1a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>(選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或說出其名稱來宣告其進入或結束。 您可以透過執行 Cmdlet 來變更宣告的運作方式。 此為選用步驟。

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改會議加入並離開宣告行為

1.  以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元執行下列動作：
    
        Get-CsDialinConferencingConfiguration
    
    這個 Cmdlet 會在加入會議時，以及 Lync Server 如何在參與者加入或離開電話撥入式會議時的回應，來檢索相關資訊。

4.  在命令提示字元執行下列動作：
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   會判斷匿名參與者是否需要在進入會議之前先記錄其名稱。 預設值為「$true」，表示加入會議時，系統會提示匿名參與者指出他們的名稱。 （經過驗證的參與者不會記錄其名稱，因為改為使用其顯示名稱。）
    
    **[EntryExitAnnouncementsEnabledByDefault**   ] 表示預設是否開啟或關閉公告。 預設值為「$false」，這表示參與者加入或離開會議時，預設沒有宣告。 會議召集人可以在排程會議時覆蓋此設定。
    
    **EntryExitAnnouncementsType**   表示每當參與者加入或離開已啟用宣告的會議時所採取的動作。 預設值為 "UseNames"，這表示您已開啟公告時的「Ken Myer 已加入會議」：
    
    您可以在全域範圍或網站範圍中設定這些設定。 在網站範圍設定的設定，會優先于在全域範圍中設定的設定。
    
    例如：
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    在這個範例中，設定是在雷德蒙的網站範圍設定。 公告已開啟，但在加入會議時，系統不會提示參與者說出其名稱。 當參與者進入或離開會議時，會播放音調。

</div>

</div>

<span> </span>

</div>

</div>

</div>

