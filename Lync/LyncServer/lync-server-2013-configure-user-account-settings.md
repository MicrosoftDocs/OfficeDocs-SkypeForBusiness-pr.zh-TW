---
title: Lync Server 2013：設定使用者帳戶設定
description: Lync Server 2013：設定使用者帳戶設定。
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
ms.openlocfilehash: e6ab4c57ba3d3e8c084314e1093736334312d0c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577509"
---
# <a name="configure-user-account-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者帳戶設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

撥入使用者輸入他們的電話號碼或分機號碼，以及將會議加入已驗證使用者的 PIN 碼。 驗證需要在 Lync Server 使用者帳戶上指定的電話語音 **行 URI** 。

本主題中的程式說明如何為單一使用者帳戶指派 **行 URI** 。 如果您需要為多個使用者帳戶指派 **行 URI** ，您可以建立使用 **Set-CsUser** Cmdlet 的腳本。 如需使用範例腳本將 **行 URI** 指派給多個使用者帳戶的詳細資訊，請參閱的「指派行 URIs 給多位使用者」 [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945) 。

<div>

## <a name="to-configure-user-account-settings"></a>設定使用者帳戶設定

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 **Cs-UserAdministrator** 或 **CsAdministrator** 角色的成員身分登入電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [搜尋] 欄位中，輸入您要設定電話撥入式會議的使用者名稱，或按一下 [ **新增篩選** ] 以指定搜尋欄位，然後按一下 [ **尋找**]。

5.  按兩下使用者名稱，以開啟 [ **編輯 Lync Server 使用者** ] 對話方塊。

6.  在 [ **電話語音**] 下的 [ **線路 URI** ] 欄位中，輸入唯一且正規化的電話號碼 (例如電話： + 14255550200) 。
    
    <div>
    

    > [!NOTE]  
    > 只有在<STRONG>電話語音</STRONG>設定為<STRONG>僅限 pc 對電腦</STRONG>、 <STRONG>Enterprise Voice</STRONG>、<STRONG>遠端呼叫控制</STRONG>或<STRONG>遠端呼叫控制</STRONG>時，您才可以指定<STRONG>行 URI</STRONG> 。

    
    </div>

7.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

