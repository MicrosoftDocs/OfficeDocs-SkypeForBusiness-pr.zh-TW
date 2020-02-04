---
title: Lync Server 2013：安裝 Operation Manager 代理程式檔
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
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>在 Lync Server 2013 中安裝 Operation Manager 代理程式檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

若要在電腦上安裝 Operations Manager 代理檔案，請完成下列步驟。

1.  在系統中心設定媒體上，按兩下 [ **SetupOM**]。

2.  在 System Center Operation Manager 設定中，按一下 [**安裝 Operations Manager 代理**程式]。

3.  在 System Center 設定向導中，在 [**歡迎使用 System Center Operations Manager 安裝程式**嚮導] 頁面上，按一下 **[下一步]**。

4.  在 [**目的地資料夾**] 頁面上，選取將安裝 Operations Manager 代理程式檔案的資料夾，然後按 **[下一步]**。

5.  在 [**管理群組**設定] 頁面上，選取 [**指定管理群組資訊**]，然後按一下 **[下一步]**。

6.  在 [**管理群組**設定] 頁面上，于 [**管理群組名稱**] 方塊中輸入 operations manager 管理群組的名稱，然後在 [**管理伺服器**] 方塊中輸入 operations manager 伺服器的主機名稱（例如 [atl-scom-001]）。 如果您已經變更了 Operations Manager 所使用的埠號，請在 [管理伺服器埠] 方塊中輸入新的埠號碼。 否則，請將埠保留為預設值5723，然後按 **[下一步]**。

7.  在 [**代理程式動作帳戶**] 頁面上，選取 [**本機系統**]，然後按一下 **[下一步]**。

8.  在 [ **Microsoft update** ] 頁面上，選取 [**我不想使用 Microsoft update**]，然後按一下 **[下一步]**。

9.  在 [**準備安裝**] 頁面上，按一下 [**安裝**]。

10. 在 [**完成 System Center Operations Manager 安裝程式嚮導]** 頁面上，按一下 **[完成]**。

11. 按一下 **[** 結束]。

如果您使用的是 System Center 2007 R2，您可以按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **System Center Operations Manager 2007 R2**]，然後按一下 [ **Operations Manager Shell**]，確認已建立代理程式。 在 Operations Manager Shell 中，輸入下列 Windows PowerShell 命令，然後按 ENTER：

    Get-Agent 

系統會在螢幕上顯示所有 Operations Manager 代理程式的清單。

如果您使用的是系統中心2012，請在 Operations 2012 管理器 Shell 中執行此命令：

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

