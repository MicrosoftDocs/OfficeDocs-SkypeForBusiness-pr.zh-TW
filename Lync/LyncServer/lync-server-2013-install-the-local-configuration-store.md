---
title: Lync Server 2013：安裝本機設定存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>在 Lync Server 2013 中安裝本機設定存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-27_

在執行下列步驟之前，請確認您已使用網域使用者帳戶登入伺服器，且這兩者都是本機管理員，且是 RTCUniversalReadOnlyAdmin 群組的成員。

若要能夠使用 Lync Server 部署嚮導執行任何動作，我們必須在伺服器上存在本機配置存放區。 本機配置存放區是集中式管理儲存體的唯讀複本，在本機安裝 SQL Server Express 之後就會建立。 中央管理商店本身會新增至安裝在標準版 server 或 SQL Server Express 資料庫上的現有 SQL Server 資料庫。

<div>


> [!IMPORTANT]  
> 如果您之前沒有在此伺服器上執行 Lync Server 2013 設定，系統會提示您輸入安裝 Lync Server 2013 的磁片磁碟機和路徑。 這可讓您安裝到系統磁片磁碟機以外的磁碟機（如果您的組織需要的話），或者您是否有空間擔心。 您只需將 [設定] 對話方塊中的 Lync Server 檔案安裝位置路徑變更為新的可用磁片磁碟機即可。 如果您將安裝檔案安裝到此路徑，包括 OCSCore，則其餘的 Lync Server 2013 檔案也會部署在該處。



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>安裝本機配置存放區

1.  從您的安裝媒體，流覽\\至\\[\\設定 Amd64] Setup.exe，然後按一下 **[確定]**。

2.  如果系統提示您安裝 Microsoft Visual c + + 2012 可轉散發元件，請按一下 **[是]**。

3.  在 [ **Lync Server 2013 安裝位置**] 頁面上，按一下 **[確定]**。

4.  在 [**使用者授權合約**] 頁面上，查看 [授權條款]，您必須選取 **[我接受授權合約中的條款**]，然後按一下 **[確定]** 以繼續進行。

5.  在 [部署嚮導] 頁面上，按一下 [**安裝或更新 Lync Server 系統**]。

6.  在 [ **Lync Server 2013** ] 頁面上，按一下 [ **Step1：安裝本機配置存放區**] 旁的 [**執行**]。

7.  在 [**安裝本機設定儲存區**] 頁面上，確認已選取 [**直接從中央管理儲存**] 選項進行檢索，然後按一下 **[下一步]**。

8.  本機伺服器設定安裝完成後，請按一下 **[完成]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

