---
title: Lync Server 2013：增強及保護伺服器和應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a>增強及保護 Lync Server 2013 的伺服器和應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-05_

您應該根據該特定元件的最佳做法，加強及保護您的作業系統和應用程式。 本節說明如何加強應用程式伺服器，並使用群組原則來實現安全性 lockdowns。

<div>


> [!NOTE]  
> 您也可以加強及保護 Microsoft Lync Server 2013 部署所用的資料庫。 如需詳細資訊，請參閱<A href="lync-server-2013-hardening-and-protecting-databases.md">強化及保護 Lync Server 2013 的資料庫</A>。



</div>

<div>

## <a name="securing-application-servers"></a>保護應用程式伺服器

針對應用程式伺服器，應加強作業系統和應用程式。 例如，專用來執行 Microsoft 網際網路安全性和加速（ISA） Server 2006 的 Windows Server 2008 電腦應該從作業系統和應用程式的觀點加強。 最小化由伺服器執行並提供的服務數目，應該是主要目標。

</div>

<div>

## <a name="securing-virtual-servers"></a>保護虛擬伺服器

虛擬伺服器快照包含伺服器資料磁片的複本，也包含記憶體內資料的轉儲，這兩者都可能包含可能會造成攻擊的敏感密碼資料。 針對使用虛擬化而實施的生產伺服器，您應該停用所有的伺服器快照，或以控制的方式進行管理。 如需安全的 Hyper-v 虛擬伺服器的詳細資料，請參閱以下網址的 Hyper-v 安全指南[http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)：。

</div>

<div>

## <a name="group-policy"></a>群組原則

在 Windows Server 2008 和 Windows Server 2008 R2 中，群組原則提供以目錄為基礎的桌面建構管理。 您可以使用群組原則，在群群組原則物件（GPO）中定義電腦和使用者設定，以執行安全性 lockdowns：

  - 以註冊表為基礎的原則

  - 安全性

  - 軟體安裝

  - 上下

  - 資料夾重新導向

  - 遠端安裝服務

為了提供管理員設定這些設定的使用者介面，系統會隨附作業系統版本、service pack 發行以及部分應用程式（包括 Lync Server 2013）隨附的系統管理範本。

Communicator .adm 檔案是一個隨附 Lync Server 2013 的系統管理範本，會安裝到% windir%\\inf\\目錄，並提供群組原則設定的介面。 Communicator. adm 中的每個設定都對應到會影響應用程式行為的註冊表中的設定。

您可以從 [Active Directory 使用者和電腦] 主機和 [群組原則管理主控台（GPMC）] 中的 [從 Gpedit.msc] 存取設定。

</div>

<div>

## <a name="group-policy-security-settings"></a>群組原則安全性設定

從 Gpedit.msc 存取 [電腦設定]/[Windows 設定]/[安全性設定] 底下，群組原則包含 GPO 的安全性設定。 您可以匯入安全性範本來設定 GPO 的安全性設定。 Windows Server 2008 安全指南，位於[http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186)與 windows Server 2008 R2 安全性合規性管理工具組[http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882)中，其中包含幾個範例範本，您可以修改這些範本來符合您的需求。

</div>

<div>

## <a name="best-practices"></a>最佳做法

  - 強化所有伺服器作業系統和應用程式。

  - 保護伺服器快照，並增強所有虛擬伺服器的安全性。

  - 使用群組原則來實施安全性 lockdowns。

</div>

</div>

<span> </span>

</div>

</div>

</div>

