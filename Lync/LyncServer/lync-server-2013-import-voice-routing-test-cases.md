---
title: Lync Server 2013：改善語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b1aba05447904d4515df7ab6137743edb52ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中改善語音路由測試案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

測試案例提供您在組織中測試語音路線的方式：您可以定義要撥打的號碼，以及要使用的撥號計畫和語音原則，而 Lync Server 2013 可以在已知這些條件下驗證，提供的號碼可以 successfully 會路由到 PSTN 網路。

您可以使用 Lync Server [控制台] 建立的測試案例通常只會儲存在當初建立並執行該案例的伺服器上。 不過，這些測試案例可以匯出為 XML 檔案（副檔名為 vtest），然後匯入到其他伺服器。 這可讓您在拓撲中不同的電腦上執行相同的測試。

<div>

## <a name="to-import-a-voice-routing-test-case"></a>若要匯入語音路由測試案例

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]。

4.  在 [**動作**] 功能表上，按一下 [匯**入測試案例**]。

5.  找出您想要匯入的測試案例檔案（vtest），然後按一下 [**開啟**]。

6.  按一下 [**認可**]，然後按一下 [**全部確認**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您匯入 vtest 檔案時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈測試案例。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中匯出語音路由測試案例](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

