---
title: '將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) '
description: 將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) 。
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
ms.openlocfilehash: e99eb445e8377a52901f54f52ca3933babe15571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559419"
---
# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) 

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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

4.  在 [定義新的中繼集區]**** 頁面上，輸入新中繼伺服器集區的 FQDN。此外，也可以選擇此集區是獨立伺服器集區或是多伺服器集區，然後按 [下一步]****。

5.  選取新中繼伺服器將要路由傳送撥入通話的下一個躍點前端伺服器集區，然後按 [下一步]****。

6.  選取中繼伺服器要使用的 Edge 集區，然後按 [下一步]****。

7.  在 [指定 PSTN 閘道]**** 頁面上，將舊的 PSTN 閘道關聯到中繼伺服器。選取閘道，然後按一下 [新增]****。

8.  按一下 [完成]****，以關閉 [定義新的中繼集區精靈]****。

9.  在 [ **拓撲**產生器] 中，選取頂端節點 [ **Lync Server 2013**]。

10. 在 [動作]**** 窗格中，選取 [發行拓撲]****，然後完成精靈。

11. 請依照部署檔中的 [在 [Lync server 2013 中安裝轉送伺服器的](lync-server-2013-install-the-files-for-mediation-server.md) 檔案] 中的步驟，在新的轉送伺服器上安裝檔案。

12. 檔案安裝至中繼伺服器後，請返回拓撲產生器，然後瀏覽左窗格中的集區。

13. 以滑鼠右鍵按一下集區，然後選取 [編輯屬性]****。

14. 在 [中繼伺服器]**** 下，清除 [組合的中繼伺服器已啟用]**** 核取方塊，然後按一下 [確定]****。

15. 在 [ **拓撲**產生器] 中，選取頂端節點 [ **Lync Server 2013**]。

16. 從 [動作]**** 功能表中，選取 [發行拓撲]****，然後完成精靈。

</div>

</div>

<span> </span>

</div>

</div>

</div>

