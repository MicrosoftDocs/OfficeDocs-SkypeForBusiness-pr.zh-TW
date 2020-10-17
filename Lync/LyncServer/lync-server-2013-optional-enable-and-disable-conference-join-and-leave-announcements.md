---
title: " (選用) 啟用和停用會議加入和離開宣告"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a50431ee1917c580440f8a47cff0ca09f5e47f07
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524430"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a> (選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

當撥入使用者加入或離開會議時，會議宣告應用程式可以透過播放音調或口述其名稱來宣告其進入或退出。 您可以透過執行 Cmdlet 來變更宣告的運作方式。 這是選擇性的步驟。

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改會議加入和離開宣告行為

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingConfiguration
    
    此 Cmdlet 會在加入會議時，檢索參與者是否需要記錄其名稱的相關資訊，以及當參與者加入或離開電話撥入式會議時，Lync Server 的回應方式。

4.  在命令提示字元中執行下列命令：
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**    決定匿名參與者是否要求在進入會議之前記錄其名稱。 預設值為 "$true，這表示匿名參與者在加入會議時，系統會提示他們輸入名稱。  (驗證的參與者不會記錄其名稱，因為會改為使用其顯示名稱。 ) 
    
    **EntryExitAnnouncementsEnabledByDefault**    會指出預設是否開啟或關閉宣告。 預設值為 "$false，這表示當參與者加入或離開會議時，預設不會有宣告。 會議召集人可以在排程會議時覆寫此設定。
    
    **EntryExitAnnouncementsType**    會指出每當參與者加入或離開已啟用宣告的會議時所採取的動作。 預設值為 "UseNames，這表示有類似下列的宣告：「Ken Myer 已加入會議」（已開啟宣告）。
    
    您可以在全域範圍或網站範圍中設定這些設定。 在網站範圍設定的設定會優先于在全域範圍設定的設定。
    
    例如：
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    在此範例中，設定是在 Redmond 的網站範圍設定。 宣告已開啟，但是參與者加入會議時，不會提示參與者說出其名稱。 當參與者進入或離開會議時，會播放音調。

</div>

</div>

<span> </span>

</div>

</div>

</div>

