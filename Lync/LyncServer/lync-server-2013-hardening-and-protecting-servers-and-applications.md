---
title: Lync Server 2013：強化及保護伺服器及應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3533bcf01338a056bab8c75d1409530fab7c901f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536880"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>強化及保護 Lync Server 2013 的伺服器和應用程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-05_

您應根據該特定元件的最佳作法來增強並保護作業系統和應用程式。 本節說明如何增強應用程式伺服器，並使用群組原則來實作安全性鎖定。

<div>


> [!NOTE]  
> 您也可以強化和保護用於 Microsoft Lync Server 2013 部署的資料庫。 如需詳細資訊，請參閱 <A href="lync-server-2013-hardening-and-protecting-databases.md">強化及保護 Lync Server 2013 的資料庫</A>。



</div>

<div>

## <a name="securing-application-servers"></a>保障應用程式伺服器的安全

若是應用程式伺服器，則應增強作業系統和應用程式。例如，專門用來執行 Microsoft Internet Security and Acceleration (ISA) Server 2006 的 Windows Server 2008 電腦應在作業系統和應用程式方面加以增強。首要目標應該是盡量減少執行的服務數量，以及伺服器提供的服務數量。

</div>

<div>

## <a name="securing-virtual-servers"></a>保障虛擬伺服器的安全

虛擬伺服器快照中包含了伺服器資料磁碟的複本，以及記憶體內部資料的傾印檔；兩者皆可能含有機密的密碼編譯資料，容易遭受攻擊。 若是以虛擬化實作的生產伺服器，則應停用所有伺服器快照，或嚴密地管理。 如需保護 Hyper-V 虛擬伺服器的詳細資訊，請參閱 Hyper-V Security Guide at： [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) 。

</div>

<div>

## <a name="group-policy"></a>群組原則

在 Windows Server 2008 和 Windows Server 2008 R2 中，群組原則提供目錄式的桌面設定管理。您可以透過在下列各項的群組原則物件 (GPO) 內定義 [電腦及使用者] 設定，使用群組原則來實作安全性鎖定：

  - 登錄型原則

  - 安全性

  - 軟體安裝

  - 指令碼

  - 資料夾重新導向

  - 遠端安裝服務

為了提供使用者介面以設定這些設定，系統管理範本隨附于作業系統版本、service pack 發行及部分應用程式（包括 Lync Server 2013）。

Communicator .adm 檔案是隨 Lync Server 2013 提供的系統管理範本，會安裝至% windir% \\ inf \\ 目錄，並提供群組原則設定的介面。 Communicator.adm 中的每一項設定都會對應到登錄中，影響應用程式行為的設定。

這些設定可以從 GPedit.dll 存取，該檔案可在 Active Directory [使用者和電腦] 主控台以及群組原則管理主控台 (GPMC) 中找到。

</div>

<div>

## <a name="group-policy-security-settings"></a>群組原則安全性設定

群組原則中包含了從 GPedit.dll 存取 GPO 時 (位於電腦設定/Windows 設定/安全性設定底下) 的安全性設定。 您可以匯入安全性範本來設定 GPO 的安全性設定。 《 Windows Server 2008 安全性指南》 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) 及 Windows server 2008 R2 安全性符合性管理工具組 [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) 包含一些範例範本，您可以修改這些範本以符合您的需求。

</div>

<div>

## <a name="best-practices"></a>最佳作法

  - 增強所有伺服器的作業系統和應用程式。

  - 保護伺服器快照並強化所有虛擬伺服器的安全性。

  - 使用群組原則實作安全性鎖定。

</div>

</div>

<span> </span>

</div>

</div>

</div>

