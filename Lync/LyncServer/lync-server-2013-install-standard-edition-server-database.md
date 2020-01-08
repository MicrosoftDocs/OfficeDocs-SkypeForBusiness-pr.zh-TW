---
title: Lync Server 2013：安裝 Standard Edition Server 資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>安裝 Lync Server 2013 的 Standard Edition Server 資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

將標準版伺服器設定為基礎結構中的唯一伺服器，讓總部使用者與其他伺服器安裝不同，因為 [**部署嚮導]** 中有專門用來設定初始伺服器的選項。

<div>

## <a name="to-install-a-standard-edition-server"></a>若要安裝標準版伺服器

1.  登入您要將標準版伺服器安裝為本機系統管理員或對等網域的伺服器。

2.  如果您尚未準備 Active Directory 網域服務，請先執行這些程式。 如需詳細資訊，請參閱[準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。

3.  在 Lync Server 部署嚮導中，按一下 [**準備第一個標準版 Server**]。

4.  在 [**準備單一標準版伺服器**] 頁面上，按一下 **[下一步]**。

5.  在 [**執行命令**] 頁面上，SQL Server 2012 Express 已安裝為中央管理儲存。 已建立必要的防火牆規則。 完成資料庫與必備軟體的安裝後，按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]  
    > 初始安裝可能需要一些時間，且 [命令輸出摘要] 畫面沒有顯示更新。 這是由 SQL Server Express 的安裝所造成。 如果您需要監視資料庫的安裝，請使用 [工作管理員] 來監視設定。

    
    </div>

6.  如果您尚未安裝 [管理工具]，請在 [Lync Server 部署嚮導] 頁面上，按一下 [**安裝拓撲**建立器]。 如需詳細資訊，請參閱[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

7.  確認 [準備 Active Directory]、「準備第一個標準版 server」和「安裝拓撲建立器」旁邊有綠色的核取記號。

</div>

</div>

<span> </span>

</div>

</div>

</div>

