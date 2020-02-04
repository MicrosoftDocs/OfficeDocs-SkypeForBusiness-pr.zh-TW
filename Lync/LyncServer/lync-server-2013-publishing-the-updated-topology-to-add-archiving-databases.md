---
title: Lync Server 2013：發佈已更新的拓撲以新增封存資料庫
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
ms.openlocfilehash: d0d12b1b4195e57fc289d11eb54f24903d05ea26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>發佈已更新的拓撲，以便在 Lync Server 2013 中新增封存資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

在拓撲建立器中更新拓撲之後，您必須先將拓撲發佈到中央管理儲存體，才能設定及使用封存。 唯讀複本會將資料複製到拓撲中的所有伺服器，以讓所有伺服器與拓撲和其他設定變更保持同步。

<div>

## <a name="to-publish-your-updated-topology"></a>發佈更新的拓撲

1.  在執行 Lync Server 2013 或已安裝 Lync Server 系統管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權利的帳戶）。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將伺服器新增到拓撲中。您必須使用<STRONG>網域系統管理員</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組成員的帳戶，且在您用於 Lync server 2013 檔案存放區之檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立員可以設定必要的隨機存取控制清單（dacl）或具有同等權利的帳戶。

    
    </div>

2.  使用拓撲建立器開啟您在前一節所建立的拓撲。

3.  在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**發佈拓撲**]。

4.  在 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。

5.  在 [**建立資料庫**] 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您沒有建立資料庫的適當許可權，您可以取消選取資料庫，且具有適當許可權的人員可以建立資料庫。 如需有關所需系統管理員許可權和許可權的詳細資訊，請參閱部署檔中的<A href="lync-server-2013-deployment-permissions-for-sql-server.md">[在 Lync server 2013 中的 SQL Server 部署許可權</A>]。<BR>只有專用 SQL Server 服務器上的資料庫才能使用拓撲建立器進行安裝。 與其他伺服器元件 collocated 之 SQL Server 服務器上的資料庫，必須透過在該電腦上執行本機安裝程式來安裝。

    
    </div>

6.  在 [**發佈嚮導完成]** 頁面上，確認拓撲已順利發佈，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 發佈拓朴之後，您必須先設定用於封存的選項和原則，才能存檔任何內容。 如需詳細資訊，請參閱在部署檔中設定<A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 中的存檔支援</A>。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

