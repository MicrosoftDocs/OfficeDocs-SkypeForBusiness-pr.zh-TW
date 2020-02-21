---
title: Lync Server 2013： 定義和設定拓撲產生器中的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 597f331ba95ee563155fdabc6b95d35367d12080
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>定義和設定拓撲中的 Lync Server 2013 的拓撲產生器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

執行拓撲產生器來定義新的拓撲或修改現有拓撲不需要在本機系統管理員或特殊權限的網域群組的成員資格。 拓撲產生器會引導您完成來定義您的拓撲，Enterprise Edition 前端集區或 Standard Edition，根據設定的需求所需的步驟。

完成並發行拓撲，您可以在伺服器上安裝 Lync Server 2013 之前，您必須使用拓撲產生器]。 下列程序包含若要定義新的拓撲所需的步驟。

<div>

## <a name="to-define-a-topology"></a>若要定義拓撲

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在拓撲產生器中，選取**新的拓撲**。 您會收到提示儲存拓撲的位置和檔案名稱。 提供的拓樸檔案有意義的名稱，並接受預設副檔名.tbxml。 按一下 [確定]****。

3.  瀏覽至您想要用來儲存新的拓撲 XML 檔案、 輸入檔案名稱，然後再按一下 [**儲存**位置。

4.  在 [**定義主要網域**] 頁面中，輸入您的組織的主要 SIP 網域名稱，然後按一下 [**下一步**。

5.  在 [**指定其他支援的網域**] 頁面中，輸入其他網域的名稱，如果有的話，然後按一下 [**下一步**。

6.  在 [**定義第一個網站**] 頁面上，輸入名稱與第一個網站的描述，然後按一下 [**下一步**。

7.  在 [**指定網站詳細資料**] 頁面中，輸入網站的位置資訊，然後按一下 [**下一步**。

8.  在**成功定義新的拓撲**] 頁面上，確定已選取 [**開啟新前端精靈當這個精靈關閉時**] 核取方塊，，然後按一下 [**完成]**。

您已定義並儲存拓撲之後，使用新前端精靈來定義前端集區或 Standard Edition 伺服器，為您的網站。 如需詳細資訊，請參閱[定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

