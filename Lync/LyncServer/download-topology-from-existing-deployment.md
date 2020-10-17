---
title: 從現有部署下載拓撲
description: 從現有的部署下載拓撲。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22d746f8faf3fdf14a44e751eeb3c88bf3eef4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551179"
---
# <a name="download-topology-from-existing-deployment"></a>從現有部署下載拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

建立 Lync Server 2013 集區時，會使用與 Lync Server 2010 相關聯的中央管理存放區。 當您在第一次使用時啟動拓撲產生器和後續的編輯會話時，系統會提示您輸入您想要拓撲產生器載入目前設定檔的位置。 因為您已經定義了 Lync Server 2010 拓撲，且已建立中央管理存放區，所以您應該選擇從現有的部署下載拓撲。 拓撲產生器會讀取資料庫，並取得目前的定義。

**從現有的部署下載拓撲**

1.  開啟 **Lync Server 部署嚮導**。

2.  在 [ **Lync Server 2013 –部署嚮導]** 頁面上，按一下 [ **安裝系統管理工具**]。

3.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013** ]，然後按一下 [ **Lync server 拓撲**產生器]。

4.  選取 [ **從現有的部署下載拓撲**]。
    
    ![部署嚮導拓撲產生器設定](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "部署嚮導拓撲產生器設定")

5.  選擇檔案名，並以預設的 redmond.tbxml 檔案類型儲存拓撲。

6.  展開 Lync Server 節點（如圖所示），以顯示部署中的各種伺服器角色。
    
    ![拓撲產生器伺服器角色一般屬性](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "拓撲產生器伺服器角色一般屬性")

</div>

<span> </span>

</div>

</div>

</div>

