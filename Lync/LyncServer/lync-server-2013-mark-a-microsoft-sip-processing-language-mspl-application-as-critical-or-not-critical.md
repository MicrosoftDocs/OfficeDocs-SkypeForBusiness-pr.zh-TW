---
title: Lync Server 2013：將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵
description: Lync Server 2013：將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1f59fb6614416c1b0e4f49a766a1373483f509d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556549"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a>在 Lync Server 2013 中將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Microsoft SIP 處理語言 (MSPL) 伺服器應用程式是僅限腳本的應用程式，使用 MSPL 指令碼語言，而不是 Microsoft Lync 2010 API。 某些 MSPL 伺服器應用程式會指定為重要。 如果腳本很重要，必須在系統啟動期間啟動腳本，Lync Server 2013 才能啟動。 如果腳本在執行 Lync Server 時失敗，則伺服器不會關機，但是會停止傳送流量至腳本，而且會在事件記錄檔中寫入錯誤。

您可以使用 Lync Server 控制台，將 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式標示為關鍵或解除標記。

並非所有腳本都支援此選項。 例如，DefaultRouting 腳本會標示為 [重要]，而且無法為 DefaultRouting 變更此選項。

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a>將 MSPL 伺服器應用程式標示為關鍵或解除標記

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **拓撲** ]，然後按一下 [ **伺服器應用程式**]。

4.  在 [ **伺服器應用程式** ] 頁面上，按一下欄標題以排序應用程式（如有需要），然後按一下您要修改的伺服器應用程式。

5.  按一下 **[動作]**。

6.  按一下 [ **標示為緊急** ] 或 [ **取消選取為重要** 的 (，也就是，如果腳本支援此選項) 。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[在 Lync Server 2013 中查看 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[管理 Lync Server 2013 拓撲](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

