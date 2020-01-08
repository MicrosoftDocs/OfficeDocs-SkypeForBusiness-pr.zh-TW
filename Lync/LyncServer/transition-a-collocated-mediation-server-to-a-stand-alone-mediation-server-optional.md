---
title: 將 collocated 中繼伺服器轉換成獨立的中繼伺服器（選用）
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>將 collocated 中繼伺服器轉換成獨立的中繼伺服器（選用）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

使用下列程式，將您的中繼伺服器（collocated 標準版伺服器或頂層端池）轉換為單一網站部署的獨立中繼伺服器。

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>將 collocated 中繼伺服器轉型到獨立的中繼伺服器

1.  從拓撲建立器開啟現有的拓撲。

2.  在左窗格中，流覽到 [**轉送池**]。

3.  以滑鼠右鍵按一下 [**轉送池**]，然後選取 [**新的中繼伺服器**]。

4.  在 [**定義新的仲介資源池**] 頁面上，提供新的中繼伺服器池的 FQDN。 此外，選取此池是單一伺服器或多重伺服器池，然後按 **[下一步]**。

5.  選取新的中繼伺服器將路由入站通話的下一個躍點前端伺服器池，然後按 **[下一步]**。

6.  選取要供中繼伺服器使用的邊緣池，然後按 **[下一步]**。

7.  在 [**指定 PSTN 閘道**] 頁面上，將舊版 PSTN 閘道與中繼伺服器進行關聯。 選取閘道，然後按一下 [**新增**]。

8.  按一下 **[完成]** ，關閉 [**定義新的仲介池**] 嚮導。

9.  從 [**拓撲**建立器] 中，選取最上方節點的**Lync Server 2013**。

10. 從 [**動作**] 窗格中，選取 [**發佈拓撲**] 並完成嚮導。

11. 請依照部署檔中的 Lync Server 2013 中的 [在 Lync server 中[安裝中繼伺服器](lync-server-2013-install-the-files-for-mediation-server.md)檔案] 中的步驟進行，以在新的中繼伺服器上安裝檔案。

12. 將檔案安裝在中繼伺服器之後，請返回 [拓撲建立器]，然後在左窗格中流覽至該池。

13. 以滑鼠右鍵按一下該池，然後選取 [**編輯屬性**]。

14. 在 [**中繼伺服器**] 底下，清除 [**啟用中繼伺服器 Collocated**的核取方塊，然後按一下 **[確定]**。

15. 從 [**拓撲**建立器] 中，選取最上方節點的**Lync Server 2013**。

16. 從 [**動作**] 功能表中，選取 [**發佈拓撲**] 並完成嚮導。

</div>

</div>

<span> </span>

</div>

</div>

</div>

