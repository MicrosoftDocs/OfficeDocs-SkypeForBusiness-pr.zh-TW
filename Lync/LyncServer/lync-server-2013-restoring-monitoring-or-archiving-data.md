---
title: Lync Server 2013：還原監控或封存資料
description: Lync Server 2013：還原監控或封存資料。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 169a5da2d606b97c7cd3f59d6cbae3d4c584e6e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575511"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>在 Lync Server 2013 中還原監控或封存資料

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

在失敗後，不需要還原監控和封存資料，就能讓 Lync Server 保持開啟狀態。 不過，如果監控和封存資料對您的組織來說很重要，您會想要在重新建立資料庫之後還原資料。

下列程式說明如何使用 SQL Server Management Studio 來還原封存或監控資料。

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>從備份檔還原監控或封存資料

1.  以本機電腦上的管理員群組成員或具有同等使用者權限的群組的成員身分，登入您要還原的伺服器。

2.  開啟 SQL Server Management Studio：按一下 [ **開始**]，依序按一下 [ **所有程式**]、[ **microsoft SQL Server 2012** ] 或 **[microsoft sql Server 2008 R2**]，然後按一下 **[sql server management Studio**]。

3.  在 [連線至伺服器]**** 中，至少提供伺服器的名稱及驗證資訊，以連線至 SQL Server 執行個體。

4.  在 [物件總管]**** 中，以滑鼠右鍵按一下 [資料庫]****，然後按一下 [還原資料庫]****。

5.  在 [選取頁面]**** 底下，按一下 [一般]****，然後在 [目的地資料庫]**** 中，選取資料庫名稱，如下所示：
    
      - 若為封存資料庫，請選取 [ **LcsLog**]。
    
      - 若為詳細通話記錄 (CDR) 資料庫，請選取 [LcsCDR]****。
    
      - 若為經驗品質 (QoE) 資料庫，請選取 [QoEMetrics]****。

6.  按一下 [來源裝置]****。

7.  在 [選取要還原的備份組]**** 底下，按一下備份檔，然後按一下 [還原]****。

8.  在 [選取頁面]**** 底下，按一下 [選項]****，確認資料檔案路徑及記錄檔路徑在正確的資料夾中，然後按一下 [確定]****。

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>確定 (ACLs) 的存取控制清單正確

1.  依序展開 [資料庫]****、封存或監控資料庫、[安全性]**** 及 [使用者]****。

2.  確認網域群組 RTCComponentUniversalServices 以使用者身分存在。

3.  如果 [ **使用者**] 底下 RTCComponentUniversalServices 不存在，請執行下列動作：
    
    1.  以滑鼠右鍵按一下 [使用者]****，然後按一下 [新增使用者]****。
    
    2.  在 **[登入名稱**] 中，輸入遺失的組名 RTCComponentUniversalServices。
    
    3.  在 [資料庫角色成員資格]**** 底下，選取 [ServerRole]**** 權限，然後按一下 [確定]****。
    
    <div>
    

    > [!NOTE]  
    > 您不需要重新啟動封存或監控服務。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

