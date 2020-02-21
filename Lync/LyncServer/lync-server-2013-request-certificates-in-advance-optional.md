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

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="a5250-102">針對 Lync Server 2013 （選用） 的預先要求憑證</span><span class="sxs-lookup"><span data-stu-id="a5250-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5250-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="a5250-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a5250-104">憑證所需的所有執行 Lync Server 2013，包括每個 Enterprise Edition 前端伺服器、 Standard Edition server、 Director、 Edge Server 和獨立中繼伺服器的內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="a5250-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="a5250-105">雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。</span><span class="sxs-lookup"><span data-stu-id="a5250-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="a5250-106">憑證需求，以及使用公用 CA 的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="a5250-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="a5250-107">Lync Server 2013 安裝程式包含 [憑證] 精靈，以方便您的要求、 指派和憑證安裝在部署期間的工作。</span><span class="sxs-lookup"><span data-stu-id="a5250-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="a5250-108">如果您想要要求之前安裝伺服器憑證 (例如，以節省時間期間實際部署的伺服器)，您可以這麼做所使用的電腦上安裝 Lync Server 2013 系統管理工具或使用的憑證要求只要您確定有可匯出的憑證，且包含所有必要的主體替代名稱，組織中定義程序。</span><span class="sxs-lookup"><span data-stu-id="a5250-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="a5250-109">預先要求憑證是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="a5250-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="a5250-110">如果您不要求他們前，您必須要求他們需要憑證的每部伺服器的安裝過程。</span><span class="sxs-lookup"><span data-stu-id="a5250-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="a5250-111">此部署 > 文件提供的安裝過程中，使用 [憑證] 精靈來要求憑證，[設定憑證的伺服器中的 Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md)、 [Lync Server 2013 中 director 設定憑證](lync-server-2013-configure-certificates-for-the-director.md)] 和[安裝 Lync Server 2013 中的中繼伺服器的檔案](lync-server-2013-install-the-files-for-mediation-server.md)區段的此部署 > 文件中所述的程序。</span><span class="sxs-lookup"><span data-stu-id="a5250-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="a5250-112">如果您在預先要求憑證時，您必須修改要匯入和指派的憑證，而不是要求他們在部署的時間，視這些章節中的憑證部署程序。</span><span class="sxs-lookup"><span data-stu-id="a5250-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5250-113">Lync Server 2013 包含支援從執行 Windows Vista、 Windows Server 的用戶端連線的 sha-256 憑證&nbsp;2008、 Windows Server&nbsp;2008年&nbsp;R2 和 Windows 7 作業系統，以及 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="a5250-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="a5250-114">為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。</span><span class="sxs-lookup"><span data-stu-id="a5250-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

