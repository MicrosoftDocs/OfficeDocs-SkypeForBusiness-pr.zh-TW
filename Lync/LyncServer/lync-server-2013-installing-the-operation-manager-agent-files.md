---
title: Lync Server 2013： 安裝 Operation Manager 代理程式檔案
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
ms.openlocfilehash: c7b658475e911d300d4ec8f6c15320e69ab71e15
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Lync Server 2013 中安裝 Operation Manager 代理程式檔案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-20 個_

若要安裝 Operations Manager 代理程式檔案的電腦上，完成下列步驟。

1.  在您的 System Center 安裝媒體上，按兩下**SetupOM.exe**。

2.  在 System Center Operation Manager 安裝程式中，按一下 [**安裝 Operations Manager 代理程式**]。

3.  在 System Center 安裝精靈]**歡迎使用 System Center Operations Manager 安裝程式**精靈頁面上，按一下 [**下一步**]。

4.  在 [**目的資料夾**] 頁面上，選取的資料夾位置的 Operations Manager 代理程式檔案將會安裝，然後按 [**下一步**。

5.  在 [**管理群組設定**] 頁面上，選取 [**指定管理群組資訊**]，然後按一下 [**下一步**。

6.  在 [**管理群組設定**] 頁面中**管理群組名稱**] 方塊中，輸入 [Operations Manager 管理群組的名稱，然後輸入您的 Operations Manager 伺服器的主機名稱 (例如，atl-cs-scom-001) 在 [**管理伺服器**] 方塊中。 如果您已變更 Operations Manager 所使用的連接埠號碼，然後在 [管理伺服器連接埠] 方塊中輸入新的連接埠號碼。 否則，保留在 5723 的預設值的連接埠，然後按一下 [**下一步**。

7.  在**代理程式動作帳戶**] 頁面上，選取 [**本機系統**]，然後按一下 [**下一步**。

8.  在**Microsoft Update** ] 頁面上，選取 [**我不想要使用 Microsoft Update**，然後再按 [**下一步**。

9.  在**安裝準備就緒]** 頁面上，按一下 [**安裝**]。

10. 在 [**正在完成 System Center Operations Manager 安裝精靈**] 頁面上，按一下 [**完成]**。

11. 按一下 **[結束]**。

如果您使用 System Center 2007 R2，您可以驗證代理程式已經建立的依序按一下 [**開始**、 [**所有程式]**、 [ **System Center Operations Manager 2007 R2**，然後按一下 [ **Operations Manager 殼層**。 在 Operations Manager 介面中，輸入下列 Windows PowerShell 命令，並按 ENTER:

    Get-Agent 

所有 Operations Manager 代理程式的清單會出現在螢幕上。

如果您使用 System Center 2012，請從 Operations 2012 Manager 殼層執行此命令：

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

