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
ms.openlocfilehash: e16d4edfb53511712c58cb41510559fcf69cfa9a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498570"
---
# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>在 Lync Server 2013 中安裝本機設定存放區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-27_

在遵循這些步驟之前，請確定您已使用本機系統管理員和 RTCUniversalReadOnlyAdmin 群組成員的網域使用者帳戶登入伺服器。

若要能夠使用 Lync Server 部署嚮導執行任何動作，我們需要在伺服器上存在本機設定存放區。 本機設定存放區是中央管理存放區的唯讀複本，它會在本機安裝 SQL Server Express 之後建立。 中央管理存放區本身會新增至安裝在 Standard Edition Server 或 SQL Server Express 資料庫上的現有 SQL Server 資料庫。

<div>


> [!IMPORTANT]  
> 如果您之前未在此伺服器上執行 Lync Server 2013 安裝程式，系統會提示您輸入要安裝 Lync Server 2013 的磁片磁碟機和路徑。 如果您的組織需要，或您有空間考慮，這會讓您安裝至系統磁片磁碟機以外的其他磁碟機。 您可以在 [安裝程式] 對話方塊中，將 Lync Server 檔案的安裝位置路徑變更為新的可用磁片磁碟機。 如果您將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他 Lync Server 2013 檔案也會部署在該路徑中。



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>安裝本機設定存放區

1.  從安裝媒體，流覽至 \\ setup \\ amd64 \\Setup.exe，然後按一下 **[確定]**。

2.  如果系統提示您安裝 Microsoft Visual c + + 2012 可轉散發元件，請按一下 **[是]**。

3.  在 [ **Lync Server 2013 安裝位置** ] 頁面上，按一下 **[確定]**。

4.  在 [ **使用者授權合約** ] 頁面上，查看授權條款，您必須選取 [ **我接受授權合約中的條款**]，然後按一下 **[確定]** 以繼續。

5.  在 [部署嚮導] 頁面上，按一下 [ **安裝或更新 Lync Server 系統**]。

6.  在 [ **Lync Server 2013** ] 頁面上，按一下 [ **步驟1：安裝本機設定存放區**] 旁邊的 [ **執行**]。

7.  在 [ **安裝本機設定存放區** ] 頁面上，確定已選取 [ **直接從中央管理存放區取得** ] 選項，然後按 **[下一步]**。

8.  當本機伺服器設定安裝完成時，您應該按一下 **[完成]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

