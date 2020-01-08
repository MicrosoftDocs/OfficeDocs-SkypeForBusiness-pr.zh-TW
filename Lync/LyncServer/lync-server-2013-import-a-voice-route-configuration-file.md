---
title: Lync Server 2013：匯入語音路由組態檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f0d523cad59ee965fa90bdf6907ea030cc8a3b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>在 Lync Server 2013 中匯入語音路由組態檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您想要儲存語音路由設定，但不發佈它，請依照下列步驟使用 Lync Server [控制台] 的 [匯出及匯入] 命令來儲存及取得語音路由設定的快照。 當您匯入語音路由設定檔（vcfg），但同時又在伺服器上對語音路由設定進行變更時，Lync Server [控制台] 中的 [**語音路由**] 群組中的頁面將會顯示 [語音路由] 中有未提交的變更。 那些未提交的變更是兩個需要調解的設定之間的差異。

如果您已對群組內任何頁面上的設定進行任何未提交的變更，這些變更就會儲存在匯出的語音設定檔案（vcfg）中。 這可讓您在發佈變更前，在多個會話期間進行語音路由設定的變更。

<div>

## <a name="to-import-a-voice-routing-configuration"></a>若要匯入語音路由設定

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]。

4.  在 [**動作**] 功能表上，按一下 [匯**入配置**]。

5.  找出您要匯入的設定檔，然後按一下 [**開啟**]。

6.  按一下 [**認可**]，然後按一下 [**全部確認**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您匯入語音設定檔案時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中匯出語音路由設定檔](lync-server-2013-export-a-voice-route-configuration-file.md)  
[在 Lync Server 2013 中發佈語音路由設定的擱置變更](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

