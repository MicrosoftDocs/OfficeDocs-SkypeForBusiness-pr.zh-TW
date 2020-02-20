---
title: 安裝 Lync Server 2013 核心檔案與 RTCLocal 資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17b3b1925607a80f143c57e6185c7a709b19ee0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>安裝 Lync Server 2013 核心檔案與 RTCLocal 資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-20 個_

若要安裝在電腦上的 Lync Server 2013 核心檔案，請完成下列程序。 當您安裝的核心檔案時，會自動安裝 RTCLocal 資料庫。 請注意，您不需要在監看員節點上安裝 SQL Server。 相反地，SQL Server Express 會自動安裝您。

若要安裝 Lync Server 2013 核心檔案與 RTCLocal 資料庫：

1.  在監看員節點電腦上，按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**、 以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。

2.  在主控台視窗中，輸入下列命令，然後按 ENTER，Lync Server 安裝程式檔案使用適當的路徑：
    
        D:\Setup.exe /BootstrapLocalMgmt

若要確認已成功安裝核心的 Lync Server 元件，按一下 [**開始]**、 [**所有程式]**、 [ **Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。 Lync Server 2013 管理命令介面中，輸入下列 Windows PowerShell 命令，並按 ENTER:

    Get-CsWatcherNodeConfiguration

第一次您執行此命令中，您不傳回任何資料是因為您有尚未設定任何監看員節點電腦上。 只要命令執行時未傳回錯誤，您可以假設 Lync Server 安裝程式順利完成。

如果您的監看員節點電腦位於周邊網路內，您可以執行下列命令來確認 Lync Server 2013 的安裝：

    Get-CsPinPolicy

您會收到類似下列命令，根據設定供組織使用的個人識別碼 (pin) 原則數量的資訊：

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

如果您看到 PIN 原則的相關的資訊，就表示您已成功安裝核心元件。

</div>

<span> </span>

</div>

</div>

</div>

