---
title: Lync Server 2013：在拓撲建置器中定義和設定拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee952eef30fc50f30448c98956899c3a1a06dc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>針對 Lync Server 2013 在拓撲建置器中定義和設定拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

執行拓撲建立器以定義新拓撲或修改現有的拓撲，不需要本機系統管理員或許可權網域群組中的成員資格。 [拓撲建立器] 會引導您完成針對企業版前端池或標準版定義拓朴所需的步驟，視您的配置需求而定。

您必須使用拓撲建立器才能完成併發布拓撲，然後才能在伺服器上安裝 Lync Server 2013。 下列套裝程式含定義新拓撲所需的步驟。

<div>

## <a name="to-define-a-topology"></a>定義拓朴

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在 [拓撲建立器] 中，選取 [**新拓撲**]。 系統會提示您輸入儲存拓撲的位置和檔案名。 為拓撲檔案指定一個有意義的名稱，並接受 tbxml 的預設副檔名。 按一下 [確定]****。

3.  流覽至您要儲存新拓撲 XML 檔案的位置，輸入檔案的名稱，然後按一下 [**儲存**]。

4.  在 [**定義主要網域**] 頁面上，輸入貴組織主要 SIP 網域的名稱，然後按 **[下一步]**。

5.  在 [**指定其他支援的網域**] 頁面上，輸入其他網域的名稱（如果有的話），然後按 **[下一步]**。

6.  在 [**定義第一個網站**] 頁面上，輸入第一個網站的名稱和描述，然後按 **[下一步]**。

7.  在 [**指定網站詳細資料**] 頁面上，輸入網站的位置資訊，然後按 **[下一步]**。

8.  在 [**新拓撲已成功定義**] 頁面上，確認已選取 [在**關閉此嚮導時開啟新的前端嚮導]** 核取方塊，然後按一下 **[完成**]。

定義並儲存拓撲之後，請使用新的 [前端] 嚮導，為您的網站定義前端池或標準版伺服器。 如需詳細資訊，請參閱[在 Lync server 2013 中定義及設定前端池或標準版伺服器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

