---
title: 變更語音路由以使用新的 Lync Server 2013 轉送伺服器
description: 變更語音路由以使用新的 Lync Server 2013 轉送伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545739"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>變更語音路由以使用新的 Lync Server 2013 轉送伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

此程式會變更語音路由以使用 Lync Server 2013 轉送伺服器，而不是舊版 Office 通訊伺服器 2007 R2 轉送伺服器。

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>變更語音路由以使用新的中繼伺服器

1.  Lync Server 2013 控制台

2.  在左窗格中，選取 [ **語音路由** ]，然後選取 [ **路由**]。

3.  按一下 [新增]****，以建立新的語音路由。

4.  填寫下列欄位：
    
      - **名稱**：輸入語音路由的描述性名稱。 若為此檔，我們會使用 **W15PSTNRoute**。
    
      - **描述**：輸入語音路由的簡短描述。

5.  略過後續的所有區段，直到 [關聯的閘道]**** 出現為止。 按一下 **[新增]**。 選取新的預設閘道，然後按一下 **[確定]**。

6.  在 [關聯的 PSTN 使用方式]**** 底下，按一下 [選取]****。

7.  從 [ **選取 PSTN 使用方式記錄** ] 頁面中，選取記錄名稱，然後按一下 **[確定]**。

8.  在 [新增語音路由]**** 頁面中，按一下 [確定]****，以建立**語音路由**。

9.  在 [語音路由]**** 頁面中，選取 [路由]****。

10. 將新建立的路由移至清單的頂端，然後選取 [ **認可**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

