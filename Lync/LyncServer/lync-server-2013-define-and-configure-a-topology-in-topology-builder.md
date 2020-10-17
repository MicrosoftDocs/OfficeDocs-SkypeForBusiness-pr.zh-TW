---
title: Lync Server 2013：在拓撲產生器中定義及設定拓撲
description: Lync Server 2013：在拓撲產生器中定義及設定拓撲。
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
ms.openlocfilehash: 83a1f29ec78cf7cfd3856d3f1aa87a22dc0bbe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569939"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>在 Lync Server 2013 的拓撲產生器中定義及設定拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

執行拓撲產生器以定義新的拓撲或修改現有的拓撲，不需要本機系統管理員或特權網域群組的成員資格。 拓撲產生器會引導您逐步完成定義 Enterprise Edition 前端集區或 Standard Edition 的拓撲所需的步驟，視您的設定需求而定。

您必須先使用拓撲產生器，才可在伺服器上安裝 Lync Server 2013，以完成併發行拓撲。 下列套裝程式含定義新拓撲所需的步驟。

<div>

## <a name="to-define-a-topology"></a>若要定義拓撲

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [拓撲產生器] 中，選取 [ **新增拓撲**]。 系統會提示您輸入儲存拓撲的位置和檔案名。 為拓撲檔案提供有意義的名稱，並接受 redmond.tbxml 的預設副檔名。 按一下 [確定]****。

3.  流覽至您要儲存新拓撲 XML 檔案的位置，輸入檔案名，然後按一下 [ **儲存**]。

4.  在 [ **定義主域** ] 頁面上，輸入組織之主要 SIP 網域的名稱，然後按 **[下一步]**。

5.  在 [ **指定其他支援的網域** ] 頁面上，輸入其他網域的名稱（如果有的話），然後按 **[下一步]**。

6.  在 [ **定義第一個網站** ] 頁面上，輸入第一個網站的名稱和描述，然後按 **[下一步]**。

7.  在 [ **指定網站詳細資料** ] 頁面上，輸入網站的位置資訊，然後按 **[下一步]**。

8.  在 [已 **成功定義新拓撲** ] 頁面上，確定已選取 [在 **此嚮導關閉時開啟新的前端嚮導]** 核取方塊，然後按一下 **[完成]**。

在您定義及儲存拓撲之後，請使用新的前端嚮導為網站定義前端集區或 Standard Edition server。 如需詳細資訊，請參閱 [在 Lync server 2013 中定義及設定前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

