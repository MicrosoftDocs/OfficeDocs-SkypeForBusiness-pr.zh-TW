---
title: Lync Server 2013：安裝 Standard Edition Server 資料庫
description: Lync Server 2013： Install Standard Edition Server database。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a20d2c01de94ad88960555db78c57c6b79d92f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574079"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>安裝 Lync Server 2013 的 Standard Edition server 資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

將 Standard Edition server 設定為您基礎結構中的唯一伺服器，而家裡的使用者與其他伺服器安裝不同，在 **部署嚮導** 中特別是用來設定初始伺服器的選項。

<div>

## <a name="to-install-a-standard-edition-server"></a>若要安裝 Standard Edition Server

1.  以本機系統管理員身分或網域對等方式，登入您要安裝 Standard Edition server 的伺服器。

2.  若尚未準備 Active Directory 網域服務，請先執行這些程式。 如需詳細資訊，請參閱 [準備 Active Directory 網域服務 For Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)。

3.  在 [Lync Server 部署嚮導] 中，按一下 [ **準備第一個 Standard Edition Server**]。

4.  在 **[準備單一 Standard Edition Server]** 頁面上，按 **[下一步]**。

5.  在 [ **執行命令** ] 頁面上，SQL Server 2012 Express 是以中央管理存放區的方式安裝。 已建立所需的防火牆規則。 在完成資料庫和必要軟體的安裝時，請按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]  
    > 如果命令輸出摘要畫面沒有可見的更新，則初始安裝可能需要一些時間。 這是因為安裝 SQL Server Express。 如果您需要監控資料庫的安裝，請使用 [工作管理員] 來監控安裝程式。

    
    </div>

6.  在 [Lync Server 部署嚮導] 頁面上，按一下 [ **安裝拓撲** 產生器] （如果先前尚未安裝系統管理工具）。 如需詳細資訊，請參閱 [Install Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

7.  確認 [準備 Active Directory]、[準備第一個 Standard Edition Server] 和 [安裝拓撲產生器] 旁邊有綠色勾號。

</div>

</div>

<span> </span>

</div>

</div>

</div>

