---
title: Lync Server 2013：發佈語音路由設定的擱置變更
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
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中發佈語音路由設定的擱置變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-07_

在您針對 [**語音路由**] 群組中的頁面變更任何設定設定之後，請執行此程式來審閱、發佈或解除擱置中的變更。

<div>


> [!IMPORTANT]  
> 確定一次只有一個使用者會修改 [語音路由設定] 設定。<BR>只要執行 [<STRONG>全部提交</STRONG>] 命令，就必須同時發佈所有擱置中的變更。 您無法選擇性地發佈擱置中的變更。 發佈待定變更之前，請先執行 [<STRONG>查看未提交的變更</STRONG>] 命令，然後取消任何您不想發佈的設定變更。<BR>如果您在提交掛起的變更前，移出 [<STRONG>語音路由</STRONG>] 群組中的頁面，所有擱置的變更都會遺失。 不過，您可以將目前的設定（包括任何擱置中的變更）匯出到語音設定檔案，然後匯入併發布更新的設定。 如需詳細資訊，請參閱<A href="lync-server-2013-export-a-voice-route-configuration-file.md">在 Lync Server 2013 中匯出語音路由設定檔</A>。



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>若要查看、發佈或取消語音路由設定變更

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]。

4.  針對 [**語音路由**] 群組的每個頁面上的設定變更您想要的設定。

5.  若要查看待定的變更而不發佈，請選取 [**確認**] 功能表中的 [**查看未提交的變更**]。

6.  如果您想要取消任何待定的變更，請執行下列其中一項操作：
    
      - 從 [**認可**] 功能表中選取 [**取消所有未提交的變更**]。
    
      - 流覽至含有您要取消之待定變更之 [**語音路由**] 頁面的索引標籤，選取含有待定變更的專案，按一下 [**認可**]，然後按一下 [**取消選取的變更**]。

7.  審閱完所有擱置的變更並取消任何不想發佈的變更之後，請按一下 [**認可**]，然後按一下 [**全部提交**]。

8.  在 [**未提交的語音設定**] 對話方塊中，顯示所有待定變更的清單，按一下 **[確定]**。
    
    當 Lync Server 控制台提交變更之後，就會出現 [**成功發佈的語音路由**設定] 訊息。

</div>

</div>

<span> </span>

</div>

</div>

</div>

