---
title: 變更語音路由以使用新的 Lync Server 2013 轉送服務伺服器
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
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>變更語音路由以使用新的 Lync Server 2013 轉送服務伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

這個程式會將語音路由變更為使用 Lync Server 2013 轉送伺服器，而不是舊版 Office 通訊伺服器 2007 R2 轉送伺服器。

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>若要變更語音路由以使用新的中繼伺服器

1.  Lync Server 2013 [控制台]

2.  在左窗格中，選取 [**語音路由**]，然後選取 [**傳送**]。

3.  按一下 [**新增**]，建立新的語音路線。

4.  填寫下欄欄位：
    
      - **Name （名稱**）：輸入語音路線的描述性名稱。 我們將在這份檔中使用**W15PSTNRoute**。
    
      - **描述**：輸入語音路線的簡短描述。

5.  略過其餘所有章節，直到您到達**關聯的閘道**為止。 按一下 [**新增**]。 選取新的預設閘道，然後按一下 **[確定]**。

6.  在 [**關聯的 PSTN 使用**] 底下，按一下 [**選取**]。

7.  從 [**選取 PSTN 使用量記錄**] 頁面，選取記錄名稱，然後按一下 **[確定]**。

8.  從 [**新增語音路由**] 頁面，按一下 **[確定]** 來建立**語音路線**。

9.  從 [**語音路由**] 頁面，選取 [**傳送**]。

10. 將新建立的路由移到清單頂端，然後選取 [Commit] （**提交**）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

