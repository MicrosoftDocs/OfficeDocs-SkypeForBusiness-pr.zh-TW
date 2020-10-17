---
title: Lync Server 2013：將暫止的變更發佈至語音路由設定
description: Lync Server 2013：將暫止的變更發佈至語音路由設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7a56b9a07606932a34dea7149a799dbb60b376
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565449"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中將擱置的變更發佈至語音路由設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-07_

變更 [ **語音路由** ] 群組中的任何設定設定後，請執行此程式以複查、發佈或取消暫止的變更。

<div>


> [!IMPORTANT]  
> 請確定一次只能有一個使用者修改語音路由設定的設定。<BR>所有擱置的變更都必須同時發佈，只要執行 [ <STRONG>全部認可</STRONG> ] 命令即可。 您無法選擇性發行暫止的變更。 在您發佈暫止的變更之前，請執行 [ <STRONG>檢查未</STRONG> 認可的變更] 命令，並取消您不想發佈的任何設定變更。<BR>如果您在提交暫止的變更之前，移離 <STRONG>語音路由</STRONG> 群組中的頁面，所有擱置的變更將會遺失。 不過，您可以將目前的設定 (包括任何擱置的變更) 至語音設定檔，然後匯入併發行更新的設定。 如需詳細資訊，請參閱 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file In Lync Server 2013</A>。



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>若要檢查、發佈或取消語音路由設定變更

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**。

4.  在 [ **語音路由** ] 群組的每一頁上進行設定的設定變更。

5.  若要在未發佈的情況下複查擱置中的變更，請選取 [從**認可**] 功能表**查看未**認可的變更

6.  如果您想要取消任何擱置的變更，請執行下列其中一項操作：
    
      - 從 [**認可**] 功能表中，選取 [**取消所有未**認可的變更]。
    
      - 流覽至 [ **語音路由** ] 頁面上的 [語音路由] 頁面，其中含有您想要取消的待處理變更，選取具有暫止變更的專案，按一下 [ **認可**]，然後按一下 [ **取消選取的變更**]。

7.  在您檢查所有擱置的變更並取消任何不想發佈的變更之後，請按一下 [ **認可**]，然後按一下 [ **全部認可**]。

8.  在 [ **未認可的語音設定** ] 對話方塊中，顯示所有擱置變更的清單，按一下 **[確定]**。
    
    當 Lync Server 控制台認可變更時，就會出現 [ **成功發行的語音路由** 設定] 訊息。

</div>

</div>

<span> </span>

</div>

</div>

</div>

