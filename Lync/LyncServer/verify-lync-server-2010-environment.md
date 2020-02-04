---
title: 驗證 Lync Server 2010 環境
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
ms.openlocfilehash: 2a871955f53515491ed09ece5e5da21ef7a9fef8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>驗證 Lync Server 2010 環境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

在使用 Lync Server 2010 的共存狀態中部署 Lync Server 2013 之前，您必須確認已設定並啟動 Lync Server 2010 服務。 在部署 Lync Server 2013 試驗池之前，請務必先找出舊版環境中存在的重要服務和功能。 在使用舊版 XMPP 部署在共存狀態中部署 Microsoft Lync Server 2013 XMPP 之前，您必須確認已設定並啟動舊版 XMPP 服務，並識別舊版 XMPP 設定支援的聯盟夥伴。 驗證舊版 Lync Server 2010 部署需要下列各項：

  - 驗證 Lync Server 2010 服務已啟動

  - 在 Lync Server 2010 中查看拓撲和使用者。

  - 驗證同盟和 Edge 伺服器設定。

  - 驗證 XMPP 服務和聯盟夥伴。

**驗證 Lync Server 2010 服務已啟動**

1.  從 Lync Server 2010 前端伺服器流覽至 [管理工具\\服務] 小程式。

2.  確認下列服務正在前端伺服器上執行：
    
    ![在前端伺服器上執行的服務清單](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "在前端伺服器上執行的服務清單")

**在 Lync Server [控制台] 中查看 Lync Server 2010 拓撲**

1.  使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。

2.  開啟 [Lync Server 控制台]。

3.  選取 [**拓撲**]。 確認您的 Lync Server 2010 部署中的各個伺服器都已列出。
    
    ![[Lync Server 2010 控制台拓撲] 頁面](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "[Lync Server 2010 控制台拓撲] 頁面")

**在 Lync Server [控制台] 中查看 Lync Server 2010 使用者**

1.  開啟 [Lync Server 控制台]。

2.  選取 [**使用者**]，然後按一下 [**尋找**]。

3.  確認 [**註冊機構池**] 欄針對列出的每位使用者，指向 [Lync Server 2010] 池。
    
    ![列出使用者的 Lync Server 2010 控制台](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "列出使用者的 Lync Server 2010 控制台")

**驗證 Lync Server 2010 Edge 與同盟設定**

1.  啟動拓撲建立器。

2.  選取 [**從現有的部署下載拓撲**。

3.  選擇檔案名，然後以預設的 tbxml 檔案類型儲存拓撲。

4.  展開 Lync Server 2010 節點，以顯示部署中的各種伺服器角色。

5.  選取 [網站] 節點，然後驗證是否已設定 [**網站同盟路由指派**] 值。
    
    ![拓撲產生器，網站同盟路由](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "拓撲產生器，網站同盟路由")

6.  接著，選取 [標準版伺服器] 或 [企業版頂層端] 池。 判斷是否已針對低於 [資源**關聯**性] 的媒體設定 Edge 池。
    
    ![顯示伺服器與集區的拓撲產生器](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "顯示伺服器與集區的拓撲產生器")

7.  最後，選取 [邊緣] 池，並識別下一個躍點池是否已設定在**下一個躍點選取範圍**下。
    
    ![拓撲產生器，下一個躍點選取範圍](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "拓撲產生器，下一個躍點選取範圍")

**驗證舊版 XMPP 聯盟合作夥伴設定**

1.  從舊版 XMPP 伺服器流覽至 [管理工具\\服務] 小程式。

2.  確認已啟動 Office 通訊伺服器 XMPP 閘道服務。
    
    ![Office Communications Server XMPP 閘道服務](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP 閘道服務")

</div>

<span> </span>

</div>

</div>

</div>

