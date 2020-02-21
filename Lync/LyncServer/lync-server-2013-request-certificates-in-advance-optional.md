---
title: Lync Server 2013： 預先要求憑證 （選用）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691efbbc1adad91ce63cfa0bca5fba6f11b5aea2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>針對 Lync Server 2013 （選用） 的預先要求憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

憑證所需的所有執行 Lync Server 2013，包括每個 Enterprise Edition 前端伺服器、 Standard Edition server、 Director、 Edge Server 和獨立中繼伺服器的內部伺服器。 雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。 憑證需求，以及使用公用 CA 的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

Lync Server 2013 安裝程式包含 [憑證] 精靈，以方便您的要求、 指派和憑證安裝在部署期間的工作。 如果您想要要求之前安裝伺服器憑證 (例如，以節省時間期間實際部署的伺服器)，您可以這麼做所使用的電腦上安裝 Lync Server 2013 系統管理工具或使用的憑證要求只要您確定有可匯出的憑證，且包含所有必要的主體替代名稱，組織中定義程序。 預先要求憑證是選擇性的。 如果您不要求他們前，您必須要求他們需要憑證的每部伺服器的安裝過程。

此部署 > 文件提供的安裝過程中，使用 [憑證] 精靈來要求憑證，[設定憑證的伺服器中的 Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md)、 [Lync Server 2013 中 director 設定憑證](lync-server-2013-configure-certificates-for-the-director.md)] 和[安裝 Lync Server 2013 中的中繼伺服器的檔案](lync-server-2013-install-the-files-for-mediation-server.md)區段的此部署 > 文件中所述的程序。 如果您在預先要求憑證時，您必須修改要匯入和指派的憑證，而不是要求他們在部署的時間，視這些章節中的憑證部署程序。

<div>


> [!NOTE]  
> Lync Server 2013 包含支援從執行 Windows Vista、 Windows Server 的用戶端連線的 sha-256 憑證&nbsp;2008、 Windows Server&nbsp;2008年&nbsp;R2 和 Windows 7 作業系統，以及 Lync Phone Edition。 為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。



</div>

</div>

<span> </span>

</div>

</div>

</div>

