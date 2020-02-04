---
title: Lync Server 2013：設定使用者帳戶設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b74056587a192ec81f0dffb0044fb76e7698960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者帳戶設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

[撥入使用者] 輸入他們的電話號碼或分機，以及將會議加入為經過驗證的使用者的 PIN。 需要在 Lync Server 使用者帳戶上指定的電話**線路 URI** ，才能進行驗證。

本主題中的程式說明如何為單一使用者帳戶指派**行 URI** 。 如果您需要為多個使用者帳戶指派**行 URI** ，您可以建立使用**move-csuser** Cmdlet 的腳本。 如需使用範例腳本將**行 URI**指派給多個使用者帳戶的詳細資料，請參閱「指派行 Uri 給多位[http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)使用者」。

<div>

## <a name="to-configure-user-account-settings"></a>設定使用者帳戶設定

1.  以 RTCUniversalServerAdmins 群組的成員或**Cs-UserAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [搜尋] 欄位中，輸入您要為電話撥入式會議設定的使用者名稱，或按一下 [**新增篩選**] 以指定搜尋欄位，然後按一下 [**尋找**]。

5.  按兩下使用者名稱以開啟 [**編輯 Lync Server 使用者**] 對話方塊。

6.  在 [**電話**] 底下的 [**行 URI** ] 欄位中，輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。
    
    <div>
    

    > [!NOTE]  
    > 只有將<STRONG>電話</STRONG>設定為 [<STRONG>僅電腦至電腦</STRONG>]、[<STRONG>企業語音</STRONG>]、[<STRONG>遠端通話控制</STRONG>] 或 [<STRONG>遠端通話控制</STRONG>] 時，才能指定 [<STRONG>行 URI</STRONG> ]。

    
    </div>

7.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

