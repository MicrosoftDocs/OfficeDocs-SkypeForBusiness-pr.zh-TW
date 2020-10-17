---
title: Lync Server 2013：發佈更新的拓撲以新增封存資料庫
description: Lync Server 2013：發佈更新的拓撲以新增封存資料庫。
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
ms.openlocfilehash: 90d1c53fb2a2dde5dde079f09b13ff4f06a659b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571449"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>發佈已更新的拓撲，以在 Lync Server 2013 中新增封存資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

在拓撲產生器中更新拓撲之後，您必須將拓撲發佈至中央管理存放區，才能設定及使用封存。 資料的唯讀複本會複製到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。

<div>

## <a name="to-publish-your-updated-topology"></a>發行更新的拓樸

1.  在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將伺服器新增至拓撲），則必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶。而且具有在您用於 Lync server 2013 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的自由存取控制清單 (dacl) ，或具有同等 (權利的帳戶。

    
    </div>

2.  使用拓撲產生器開啟您在上一節中建立的拓撲。

3.  在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **發行拓撲**]。

4.  在 **[發行拓樸]** 頁面上，按一下 **[下一步]**。

5.  在 **[建立資料庫]** 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您未具備建立資料庫的適當權限，可以取消選取資料庫，讓具備適當權限的人能夠建立資料庫。 如需有關必要系統管理員權力與許可權的詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">SQL Server 的部署許可權（Lync server 2013</A> ）。<BR>只有專用 SQL Server 服務器上的資料庫才能使用拓撲產生器進行安裝。 與其他伺服器元件組合的 SQL Server 服務器上的資料庫，必須透過在該電腦上執行本機安裝程式來安裝。

    
    </div>

6.  在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 發行拓樸之後，您必須先為封存設定選項和原則，才能封存內容。 如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013</A> 中設定封存支援。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

