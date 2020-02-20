---
title: （選用）啟用和停用會議加入和離開宣告
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
ms.openlocfilehash: 67939f67e90e6c0cc044ea871560647cae9e4021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>（選用）啟用和停用會議加入和離開宣告在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-30_

當撥入使用者加入或離開會議時，會議宣告應用程式可以宣布其進入或結束播放音零或說他們的名稱。 您可以變更執行 cmdlet 的宣告運作方式。 此步驟是選用的。

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>若要修改會議加入和離開宣告行為

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingConfiguration
    
    此 cmdlet 會擷取參與者是否需要記錄其姓名加入會議時，與 Lync Server 時參與者加入或離開電話撥入式會議的回應資訊。

4.  在命令提示字元中執行下列命令：
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   決定匿名參與者上當系統要記錄其姓名進入會議之前。 預設值為 「 $true 」 這表示，提示匿名參與者加入會議時的狀態其名稱。 （已驗證的參與者未記錄其姓名因為可以改為使用其顯示名稱。）
    
    **EntryExitAnnouncementsEnabledByDefault**   宣告是否會開啟或關閉，預設會指示。 預設值為 「 $false 」 表示預設有任何宣告時參與者加入或離開會議。 排程會議時，會議召集人可以覆寫此設定。
    
    **EntryExitAnnouncementsType**   表示每當參與者加入或離開宣告已啟用的會議時所採取的動作。 預設值是 「 UseNames，「 這就表示有宣告如下: 「 Ken Myer 已加入會議 」 宣告已開啟。
    
    在全域範圍，或在網站範圍，您可以設定這些設定。 在網站範圍設定的設定優先於在全域範圍設定的設定。
    
    例如：
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    在這個範例中，設定是在 Redmond 的網站範圍設定。 宣告開啟狀態，但參與者系統不會提示他們加入會議時，說出其名稱。 當參與者進入或離開會議時，就會播放音。

</div>

</div>

<span> </span>

</div>

</div>

</div>

