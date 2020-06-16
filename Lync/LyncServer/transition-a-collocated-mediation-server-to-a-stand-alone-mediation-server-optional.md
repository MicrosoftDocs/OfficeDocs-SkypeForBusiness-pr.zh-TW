---
title: 將組合的轉送伺服器轉換成獨立轉送伺服器（選用）
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce0228edacba502161c4d44a6a94b38cede6655
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>將組合的轉送伺服器轉換成獨立轉送伺服器（選用）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

使用下列程序來將 Standard Edition Server 或前端集區上組合的中繼伺服器轉換成獨立中繼伺服器，以用於單一網站部署。

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>將組合的中繼伺服器轉換成獨立中繼伺服器

1.  從拓撲產生器開啟現有拓撲

2.  在左窗格中，瀏覽至 [中繼集區]****。

3.  以滑鼠右鍵按一下 [中繼集區]****，然後選取 [新增中繼伺服器]****。

4.  On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.

5.  選取新中繼伺服器將要路由傳送撥入通話的下一個躍點前端伺服器集區，然後按 [下一步]****。

6.  選取中繼伺服器要使用的 Edge 集區，然後按 [下一步]****。

7.  On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.

8.  按一下 [完成]****，以關閉 [定義新的中繼集區精靈]****。

9.  在 [**拓撲**產生器] 中，選取頂端節點 [ **Lync Server 2013**]。

10. 在 [動作]**** 窗格中，選取 [發行拓撲]****，然後完成精靈。

11. 請依照部署檔中的 [在[Lync server 2013 中安裝轉送伺服器的](lync-server-2013-install-the-files-for-mediation-server.md)檔案] 中的步驟，在新的轉送伺服器上安裝檔案。

12. 檔案安裝至中繼伺服器後，請返回拓撲產生器，然後瀏覽左窗格中的集區。

13. 以滑鼠右鍵按一下集區，然後選取 [編輯屬性]****。

14. 在 [中繼伺服器]**** 下，清除 [組合的中繼伺服器已啟用]**** 核取方塊，然後按一下 [確定]****。

15. 在 [**拓撲**產生器] 中，選取頂端節點 [ **Lync Server 2013**]。

16. 從 [動作]**** 功能表中，選取 [發行拓撲]****，然後完成精靈。

</div>

</div>

<span> </span>

</div>

</div>

</div>

