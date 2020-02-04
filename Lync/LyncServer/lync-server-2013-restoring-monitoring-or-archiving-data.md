---
title: Lync Server 2013：還原監視或封存資料
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
ms.openlocfilehash: 9621fe3c1905dbd34fd3b4da39b2562c608d6355
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>在 Lync Server 2013 中還原監視或封存資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

在失敗之後，不需要還原監視及封存資料，就能讓 Lync Server 正常運作。 不過，如果監視及封存資料對您的組織而言至關重要，您會想要在重新建立資料庫之後，還原資料。

下列程式說明如何使用 SQL Server Management Studio 來還原存檔或監視資料。

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>從備份檔案還原監視或封存資料

1.  以本機電腦上的管理員群組成員或具有同等使用者權利的群組登入您要還原的伺服器。

2.  開啟 SQL Server Management Studio：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft SQL Server 2012** ] 或 [ **microsoft sql Server 2008 R2**]，然後按一下 **[SQL server Management studio**]。

3.  在 **[連線至伺服器]** 中，至少提供伺服器名稱和驗證資訊，即可連線至 SQL Server 實例。

4.  在**物件資源管理器**中，以滑鼠右鍵按一下 [**資料庫**]，然後按一下 [**還原資料庫**]。

5.  在 [**選取頁面**] 底下，按一下 **[一般**]，然後在 [**至資料庫**] 中，選取資料庫名稱，如下所示：
    
      - 針對封存資料庫，請選取 [ **LcsLog**]。
    
      - 如需通話詳細資料錄製（CDR）資料庫，請選取 [ **LcsCDR**]。
    
      - 如需體驗品質（QoE）資料庫，請選取 [ **QoEMetrics**]。

6.  按一下 [**從裝置**]。

7.  在 **[選取要還原的備份組**] 底下，按一下備份檔案，然後按一下 [**還原**]。

8.  在 [**選取頁面**] 底下，按一下 [**選項**]，確認資料檔案路徑和記錄路徑都位於正確的資料夾中，然後按一下 **[確定]**。

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>確定存取控制清單（Acl）正確無誤

1.  展開 [**資料庫**]，展開 [封存] 或 [監控] 資料庫，展開 [**安全性**]，然後展開 [**使用者**]。

2.  確認網域群組 RTCComponentUniversalServices 以使用者的身分存在。

3.  如果 [**使用者**] 底下不存在 RTCComponentUniversalServices，請執行下列動作：
    
    1.  以滑鼠右鍵按一下 [**使用者**]，然後按一下 [**新增使用者**]。
    
    2.  在 **[登入名稱**] 中，輸入遺失的群組名稱，RTCComponentUniversalServices。
    
    3.  在 [**資料庫角色成員資格**] 底下，選取 [ **ServerRole** ] 許可權，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 您不需要重新開機存檔或監視服務。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

