---
title: 確認 Lync Server 2010 環境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce56a23120df813d3c3d8107de67d202afb5d663
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>確認 Lync Server 2010 環境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

在部署前處於共存狀態 」 與 Lync Server 2010 中的 Lync Server 2013，您需要確認 Lync Server 2010 服務已設定且啟動。 請務必識別主要服務和存在於舊版環境，再部署 Lync Server 2013 試驗集區中的功能。 之前部署 Microsoft Lync Server 2013 XMPP 處於共存狀態與舊版 XMPP 部署，您必須確認舊版 XMPP 服務已設定並開始，並識別舊版 XMPP 設定為支援的同盟協力廠商。 確認舊版 Lync Server 2010 部署需要下列：

  - 確認 Lync Server 2010 服務已啟動

  - 檢閱的拓撲和 Lync Server 2010 中的使用者。

  - 確認同盟和 Edge server 設定。

  - 確認 XMPP 服務和同盟協力廠商。

**確認 Lync Server 2010 服務已啟動**

1.  從 Lync Server 2010 前端伺服器，瀏覽至 [系統管理工具]\\服務] 小程式。

2.  確認下列服務正在執行前端伺服器上：
    
    ![在前端伺服器上執行的服務清單](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "在前端伺服器上執行的服務清單")

**檢閱 Lync Server Control Panel 中的 Lync Server 2010 拓撲**

1.  使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。

2.  開啟 Lync Server Control Panel。

3.  選取 [**拓撲**]。 確認 Lync Server 2010 部署中的各種伺服器已列出。
    
    ![Lync Server 2010 控制台拓撲] 頁面上](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 控制台拓撲] 頁面上")

**若要檢閱 Lync Server Control Panel 中的 Lync Server 2010 使用者**

1.  開啟 Lync Server Control Panel。

2.  選取 [**使用者**]，然後按一下 [**尋找**]。

3.  確認 [**登錄器集區**] 欄中指向列出每個使用者的 Lync Server 2010 集區。
    
    ![列出使用者的 Lync Server 2010 Control Panel](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "列出使用者的 Lync Server 2010 Control Panel")

**若要確認 Lync Server 2010 Edge 和同盟設定**

1.  啟動拓撲產生器]。

2.  選取 [**從現有部署下載拓撲**]。

3.  選擇 [檔案名稱，預設的.tbxml 檔案類型儲存拓撲。

4.  展開 [Lync Server 2010] 節點，顯示部署中的各種伺服器角色。

5.  選取 [網站] 節點，並確認已設定**站台同盟路由指派**值。
    
    ![拓撲產生器中，站台同盟路由](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓撲產生器中，站台同盟路由")

6.  下一步]，選取 [Standard Edition Server 或 Enterprise Edition 前端集區]。 判斷是否已設定媒體下方**關聯**Edge 集區。
    
    ![顯示伺服器和集區的拓撲產生器](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "顯示伺服器和集區的拓撲產生器")

7.  最後，選取 [Edge 集區並識別是否有設定**下一個躍點選取範圍**的下一個躍點集區。
    
    ![拓撲產生器中下, 一個躍點選取範圍](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓撲產生器中下, 一個躍點選取範圍")

**確認舊版 XMPP 同盟協力廠商設定**

1.  從舊版 XMPP 伺服器瀏覽至系統管理工具\\服務] 小程式。

2.  確認 Office Communications Server XMPP 閘道服務已啟動。
    
    ![Office Communications Server XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 閘道服務")

</div>

<span> </span>

</div>

</div>

</div>

