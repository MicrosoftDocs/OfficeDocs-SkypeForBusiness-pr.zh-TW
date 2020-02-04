---
title: Lync Server 2013：匯出語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 781c9e312044193cb6195ee849a880bea6e08485
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>在 Lync Server 2013 中匯出語音路由測試案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

測試案例可讓您在組織中測試語音路線：您可以定義要撥打的號碼，以及要使用的撥號方案和語音原則，然後 Lync Server 就能驗證所提供的號碼是否符合這些條件成功地路由到 PSTN 網路。

您可以使用 Lync Server [控制台] 建立的測試案例通常只會儲存在當初建立並執行該案例的伺服器上。 不過，這些測試案例可以匯出為 XML 檔案（副檔名為 vtest），然後匯入到其他伺服器。 這可讓您在拓撲中不同的電腦上執行相同的測試。

<div>

## <a name="to-export-a-voice-routing-test-case"></a>匯出語音路由測試案例

1.  在 Lync Server [控制台] 中，按一下 [**語音路由**]，然後按一下 [**測試語音路由**]。

2.  在 [**測試語音路由**] 索引標籤上，選取要匯出的測試案例（或測試案例）。 若要選取多個測試案例，請按一下要匯出的第一個 case，然後按住 Ctrl 鍵並選取要匯出的其他案例。

3.  按一下 [**動作**]，然後按一下 [**匯出測試案例**]。

4.  在 [**另存**新檔] 對話方塊中，選取儲存已匯出測試案例的資料夾，並在 [檔案名] 方塊中輸入所產生之 XML**檔案的名稱**。 請注意，如果您要匯出多個測試案例，所有這些測試案例都會儲存在單一 XML 檔案中。

5.  若要儲存測試案例，請按一下 [**儲存**]。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中改善語音路由測試案例](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

