---
title: Lync Server 2013：Windows PowerShell 和 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell 和 Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-20_

在 Microsoft Lync Server 2013 中，管理工具是使用 Windows PowerShell 來實現。 Windows PowerShell 包含命令列環境、產品特定命令及完整的腳本撰寫語言。 使用 Windows PowerShell 實現的 Lync Server 2013 工具組括下列各項：

  - **拓撲**建立器。 您可以使用 [拓撲建立器] 來建立、調整及發佈規劃的拓撲，並在開始伺服器安裝之前驗證您的拓撲。 當您在個別伺服器上安裝 Lync Server 2013 時，伺服器會讀取已發佈的拓撲，做為安裝程式的一部分，而安裝程式會以拓撲中的指示方式來部署伺服器。 安裝完成後，系統會自動將配置資訊複製到所有伺服器。 只有使用拓撲建立器，才能將元件新增至您的部署。

  - **Lync Server 管理命令**介面。 您可以使用 Lync Server 管理命令介面進行部署的完整命令列管理。

  - **Lync Server [控制台**]。 您可以使用 Microsoft Lync Server 2013 的 [控制台] 使用者介面來管理部署中最常見的工作。

這些工具使用 Windows PowerShell Cmdlet 來管理您的部署，包括關閉至550產品專用的 Cmdlet。 Lync Server 2013 中包含的安全性 Cmdlet 主要是用來管理驗證，以及使用者權利和許可權。 有多種不同的 Cmdlet 可用於管理驗證，包括憑證和個人識別碼（PIN）驗證的 Cmdlet。 此外，有許多 Cmdlet 可讓您使用新的角色存取控制（RBAC）功能來委派 Lync Server 2013 的管理控制權。 如需 Lync Server Cmdlet 的詳細資訊，請參閱[Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。

Windows PowerShell 的腳本安全性功能是專門設計來協助避免舊版技術的一些腳本相關安全性問題，包括 Microsoft Visual Basic 腳本版本（VBScript）。 Windows PowerShell 安全性功能是用來建立使用者無法輕易或無意中執行腳本的環境。 根據預設，會啟用 Windows PowerShell 安全性功能。 您可以修改這些功能的狀態，以適應您的腳本需求，以及各種安全目標。 這不是說 shell 無法讓使用者執行腳本。 相反地，shell 會讓使用者在執行腳本時不會有任何困難（預設），而不會意識到這麼做。 如需詳細資訊，請參閱 Windows PowerShell [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)腳本安全性。

</div>

<span> </span>

</div>

</div>

</div>

