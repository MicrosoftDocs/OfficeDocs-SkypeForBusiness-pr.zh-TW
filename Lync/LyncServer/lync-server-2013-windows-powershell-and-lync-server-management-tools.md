---
title: Lync Server 2013： Windows PowerShell 和 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24a94bf74b2ecf911179d64691e95153acceeeb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell 和 Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-20_

在 Microsoft Lync Server 2013 中，管理工具是使用 Windows PowerShell 來執行。 Windows PowerShell 包含命令列環境、產品特有的命令，以及完整的指令碼語言。 使用 Windows PowerShell 執行的 Lync Server 2013 工具組括下列各項：

  - **拓撲**產生器。 您可以使用拓撲產生器來建立、調整和發行您規劃的拓撲，並在開始伺服器安裝之前驗證拓撲。 當您在個別伺服器上安裝 Lync Server 2013 時，伺服器會在安裝程式中讀取已發佈的拓撲，而安裝程式會以拓撲中的導向方式來部署伺服器。 設定完成後，設定資訊會自動複寫到所有伺服器。 只有使用拓撲產生器，才能將元件新增至部署。

  - **Lync Server 管理命令**介面。 您可以使用 Lync Server 管理命令介面來進行部署的完整命令列管理。

  - **Lync Server 控制台**。 您可以使用 Microsoft Lync Server 2013 控制台使用者介面管理部署中的最常見工作。

這些工具使用 Windows PowerShell Cmdlet 來管理您的部署，包含接近550產品特有的 Cmdlet。 Lync Server 2013 中包含的安全性 Cmdlet 主要是用來管理驗證，以及使用者權利和許可權。 有各種各樣的指令程式可用於管理驗證，包括憑證和個人識別碼 (PIN) 驗證的 Cmdlet。 此外，一些 Cmdlet 可讓您使用新的 Role-Based 存取控制 (RBAC) 功能委派 Lync Server 2013 的管理控制。 如需 Lync Server Cmdlet 的詳細資訊，請參閱 [Lync server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面。

Windows PowerShell 的腳本安全性功能是專門設計來協助避免舊版技術（包括 Microsoft Visual Basic Script Edition (VBScript) ）的腳本相關安全性問題。 Windows PowerShell 的安全性功能主要是用來建立使用者無法輕易或無意中執行腳本的環境。 依預設，Windows PowerShell 的安全性功能都會啟用。 您可以修改這些功能的狀態，以滿足您的腳本需求和各種安全性目標。 這並不是說命令介面讓使用者無法執行腳本。 相反地，命令介面會使使用者在執行腳本時不會有這麼大的難度。 如需詳細資訊，請參閱 Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) 。

</div>

<span> </span>

</div>

</div>

</div>

