---
title: Lync Server 2013： 還原監控或封存資料
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
ms.openlocfilehash: 4e44bf1fe66aa7c03caea2ba367f425f1094a9a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>還原監控或封存 Lync Server 2013 中的資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-18_

還原監控和封存資料不是必要開始 Lync 伺服器和執行失敗之後。 不過，如果貴組織的關鍵監控和封存資料，您想重新建立資料庫之後還原資料。

下列程序說明如何使用 SQL Server Management Studio 還原封存或監控資料。

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>從備份檔還原監控或封存資料

1.  登入您要還原之本機電腦上的管理員群組或具有相等使用者權限的群組成員身分的伺服器。

2.  開啟 SQL Server Management Studio： 按一下 [**開始]**、 [**所有程式]**、 按一下 [ **Microsoft SQL Server 2012** ] 或 [ **Microsoft SQL Server 2008 R2**，，然後按一下**SQL Server Management Studio**。

3.  在 [連線至伺服器]**** 中，至少提供伺服器的名稱及驗證資訊，以連線至 SQL Server 執行個體。

4.  在 [物件總管]**** 中，以滑鼠右鍵按一下 [資料庫]****，然後按一下 [還原資料庫]****。

5.  在 [選取頁面]**** 底下，按一下 [一般]****，然後在 [目的地資料庫]**** 中，選取資料庫名稱，如下所示：
    
      - 封存資料庫中，選取 [ **LcsLog**]。
    
      - 若為詳細通話記錄 (CDR) 資料庫，請選取 [LcsCDR]****。
    
      - 若為經驗品質 (QoE) 資料庫，請選取 [QoEMetrics]****。

6.  按一下 [來源裝置]****。

7.  在 [選取要還原的備份組]**** 底下，按一下備份檔，然後按一下 [還原]****。

8.  在 [選取頁面]**** 底下，按一下 [選項]****，確認資料檔案路徑及記錄檔路徑在正確的資料夾中，然後按一下 [確定]****。

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>若要確定存取控制清單 (Acl) 正確無誤

1.  依序展開 [資料庫]****、封存或監控資料庫、[安全性]**** 及 [使用者]****。

2.  確認網域群組 RTCComponentUniversalServices 以使用者身分存在。

3.  如果 RTCComponentUniversalServices 不存在 [**使用者]**，請執行下列動作：
    
    1.  以滑鼠右鍵按一下 [使用者]****，然後按一下 [新增使用者]****。
    
    2.  在 [**登入名稱**] 中，輸入遺失的群組名稱 RTCComponentUniversalServices。
    
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

