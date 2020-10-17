---
title: Lync Server 2013：啟用或停用 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式
description: Lync Server 2013：啟用或停用 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f919599d6c6a39fea73424f4e287f00636c0982
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544779"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

您可以使用 Lync Server 控制台，啟用或停用您的 Lync Server 2013 環境中執行的 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式。 這些應用程式是使用指令碼語言，而不是 Microsoft Lync 2013 預覽 API 的腳本型應用程式。

並非所有腳本都可以啟用或停用。 例如，DefaultRouting 腳本已啟用，且無法變更 DefaultRouting 的此選項。

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a>啟用或停用 MSPL 伺服器應用程式

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **拓撲** ]，然後按一下 [ **伺服器應用程式**]。

4.  在 [ **伺服器應用程式** ] 頁面上，按一下欄標題以排序應用程式（如有需要），然後按一下您要修改的伺服器應用程式。

5.  按一下 **[動作]**。

6.  按一下 [ **啟用應用程式** ] 或 [ **停用應用程式** (，也就是，如果腳本支援此選項) 。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[在 Lync Server 2013 中查看 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[管理 Lync Server 2013 拓撲](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

