---
title: Lync Server 2013：安裝 Operation Manager 代理程式檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0216c05dd039f907d0ac54ff8afa13f6015a923d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534800"
---
# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>在 Lync Server 2013 中安裝 Operation Manager 代理程式檔案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

若要在電腦上安裝 Operations Manager 代理程式檔案，請完成下列步驟。

1.  在 System Center 安裝媒體上，按兩下 [ **SetupOM.exe**]。

2.  在 System Center operations Manager 安裝程式中，按一下 [ **安裝 Operations Manager 代理程式**]。

3.  在 [System Center 安裝精靈] 的 [ **歡迎使用 System Center Operations Manager 安裝** 嚮導] 頁面上，按 **[下一步]**。

4.  在 [ **目的地資料夾** ] 頁面上，選取將安裝 Operations Manager 代理程式檔案的資料夾，然後按 **[下一步]**。

5.  在 [ **管理群組** 設定] 頁面上，選取 [ **指定管理群組資訊**]，然後按 **[下一步]**。

6.  在 [ **管理群組** 設定] 頁面上的 [ **管理組名** ] 方塊中，輸入 operations manager 管理群組的名稱，然後在 [ **管理伺服器** ] 方塊中輸入 operations manager 伺服器的主機名稱 (例如，atl-ws-01-scom-001) 。 如果您已變更 Operations Manager 使用的埠號碼，請在 [管理伺服器埠] 方塊中輸入新的埠號碼。 否則，保留預設值5723的埠，然後按 **[下一步]**。

7.  在 [ **代理程式動作帳戶** ] 頁面上，選取 [ **本機系統**]，然後按 **[下一步]**。

8.  在 [ **Microsoft update** ] 頁面上，選取 [ **我不想使用 Microsoft Update**]，然後按 **[下一步]**。

9.  在 [ **準備安裝** ] 頁面上，按一下 [ **安裝**]。

10. 在 [ **完成 System Center Operations Manager 安裝精靈]** 頁面上，按一下 **[完成]**。

11. 按一下 **[結束]**。

如果您使用 System Center 2007 R2，您可以先依序按一下 [ **開始**]、[ **所有程式**]、[ **System Center Operations Manager 2007 R2**]，然後按一下 [ **Operations Manager 命令**介面] 來驗證代理程式是否已建立。 在 Operations Manager 命令介面中，輸入下列 Windows PowerShell 命令，然後按 ENTER：

    Get-Agent 

所有 Operations Manager 代理程式的清單都會出現在螢幕上。

如果您使用的是 System Center 2012，請從 Operations 2012 Manager 命令介面執行下列命令：

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

