---
title: Lync Server 2013： 發佈更新過的拓撲，以新增封存資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543ee664aeb8f2d8688fd35f7591726c9c0c7392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>發佈更新過的拓撲，以在 Lync Server 2013 中新增封存資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

在更新之後您在拓撲產生器的拓撲，您必須中央管理存放區發行拓撲，您可以設定及使用封存之前。 資料的唯讀複本會複製到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。

<div>

## <a name="to-publish-your-updated-topology"></a>發行更新的拓樸

1.  在執行 Lync Server 2013 中，或在 Lync Server 系統管理工具安裝上使用本機 Users 群組成員的帳戶 （或具有相等使用者權限的帳戶） 登入電腦。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於本機 Users 群組，帳戶來定義拓撲，但是若要發行拓撲，也就是必要的伺服器新增至拓撲，您必須使用屬於<STRONG>Domain Admins</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組的成員，且您使用 Lync Server 2013 檔案存放區 （亦即，以便拓撲產生器可以設定必要的判別存取控制清單 (Dacl) 的檔案共用具有完整控制權限 （亦即，讀取、 寫入及修改） 的帳戶或具有相等的權限的帳戶。

    
    </div>

2.  開啟您在前一節使用拓撲產生器中建立的拓樸。

3.  在主控台樹狀目錄中，以滑鼠右鍵按一下 [ **Lync Server 2013**中，，，然後按一下 [**發行拓撲**。

4.  在 **[發行拓樸]** 頁面上，按一下 **[下一步]**。

5.  在 **[建立資料庫]** 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您未具備建立資料庫的適當權限，可以取消選取資料庫，讓具備適當權限的人能夠建立資料庫。 如需必要的系統管理員權限與權限的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013 中的 SQL Server 的部署權限</A>。<BR>只有在專用的 SQL Server 伺服器上的資料庫可使用拓撲產生器安裝。 與其他伺服器元件組合的 SQL Server 伺服器上的資料庫必須安裝在該電腦上執行本機安裝程式。

    
    </div>

6.  在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 發行拓樸之後，您必須先為封存設定選項和原則，才能封存內容。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 中的封存設定支援</A>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

