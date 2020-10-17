---
title: 驗證 Lync Server 2010 環境
description: 驗證 Lync Server 2010 環境。
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
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555579"
---
# <a name="verify-lync-server-2010-environment"></a>驗證 Lync Server 2010 環境

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

在使用 Lync Server 2010 的共存狀態中部署 Lync Server 2013 之前，您必須確認已設定並啟動 Lync Server 2010 服務。 在部署 Lync Server 2013 試驗集區之前，請務必先識別舊環境中存在的重要服務和功能。 在採用舊版 XMPP 部署的共存狀態中部署 Microsoft Lync Server 2013 XMPP 之前，您必須確認舊版 XMPP 服務已設定並啟動，並識別舊版 XMPP 設定所支援的同盟合作夥伴。 驗證舊版 Lync Server 2010 部署需要下列專案：

  - 驗證是否已啟動 Lync Server 2010 服務

  - 在 Lync Server 2010 中查看拓撲和使用者。

  - 驗證同盟及 Edge server 設定。

  - 驗證 XMPP 服務和同盟協力廠商。

**驗證是否已啟動 Lync Server 2010 服務**

1.  從 Lync Server 2010 前端伺服器，流覽至 [系統管理工具 \\ 服務] 小程式。

2.  確認下列服務正在前端伺服器上執行：
    
    ![前端伺服器上執行的服務清單](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "前端伺服器上執行的服務清單")

**在 Lync Server 控制台中檢查 Lync Server 2010 拓撲**

1.  使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。

2.  開啟 Lync Server 控制台。

3.  選取 [ **拓撲**]。 確認您的 Lync Server 2010 部署中的各種伺服器都已列出。
    
    ![Lync Server 2010 控制台拓撲頁面](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 控制台拓撲頁面")

**在 Lync Server 控制台中檢查 Lync Server 2010 使用者**

1.  開啟 Lync Server 控制台。

2.  選取 [ **使用者** ]，然後按一下 [ **尋找**]。

3.  確認 [ **註冊集** 區] 欄針對所列的每位使用者，指向 [Lync Server 2010 集區]。
    
    ![Lync Server 2010 控制台，列出使用者](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 控制台，列出使用者")

**驗證 Lync Server 2010 Edge 及同盟設定**

1.  啟動拓撲產生器。

2.  選取 [ **從現有的部署下載拓撲**]。

3.  選擇檔案名，並以預設的 redmond.tbxml 檔案類型儲存拓撲。

4.  展開 Lync Server 2010 節點，以顯示部署中的各種伺服器角色。

5.  選取 [網站] 節點，並確認是否已設定 [ **網站同盟路由指派** ] 值。
    
    ![拓撲產生器的網站同盟路由](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓撲產生器的網站同盟路由")

6.  接下來，選取 [Standard Edition Server] 或 [Enterprise Edition 前端集區]。 判斷是否已針對下層 **關聯**的媒體設定 Edge 集區。
    
    ![顯示伺服器和集區的拓撲產生器](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "顯示伺服器和集區的拓撲產生器")

7.  最後，選取 Edge 集區，並識別下一個躍點集區是否已在 **下一個躍點選取範圍**下設定。
    
    ![拓撲產生器，下一個躍點選取範圍](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓撲產生器，下一個躍點選取範圍")

**驗證舊版 XMPP 同盟協力廠商設定**

1.  在舊版 XMPP 伺服器上，流覽至 [系統管理工具 \\ 服務] 小程式。

2.  確認已啟動 Office 通訊伺服器 XMPP 閘道服務。
    
    ![Office 通訊伺服器 XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office 通訊伺服器 XMPP 閘道服務")

</div>

<span> </span>

</div>

</div>

</div>

