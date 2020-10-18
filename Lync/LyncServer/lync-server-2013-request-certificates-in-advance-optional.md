---
title: 'Lync Server 2013：事先要求憑證 (選用) '
description: Lync Server 2013：預先要求憑證 (選用) 。
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
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579029"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="eae99-103">在 Lync Server 2013 的預先 (選用) 中預先要求憑證</span><span class="sxs-lookup"><span data-stu-id="eae99-103">Request certificates in advance (optional) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae99-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="eae99-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="eae99-105">所有執行 Lync Server 2013 的內部伺服器都必須有憑證，包含每個 Enterprise Edition 前端伺服器、Standard Edition Server、Director、Edge Server 和獨立轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="eae99-105">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="eae99-106">雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。</span><span class="sxs-lookup"><span data-stu-id="eae99-106">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="eae99-107">如需憑證需求的詳細資訊，以及使用公用 CA，請參閱規劃檔中的 [Lync Server 2013 內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md) 。</span><span class="sxs-lookup"><span data-stu-id="eae99-107">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="eae99-108">Lync Server 2013 安裝套裝程式含憑證嚮導，可協助在部署期間要求、指派及安裝憑證的工作。</span><span class="sxs-lookup"><span data-stu-id="eae99-108">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="eae99-109">如果您想要在安裝伺服器之前要求憑證 (例如，若要在實際部署伺服器期間節省時間) ，您可以使用已安裝 Lync Server 2013 系統管理工具的電腦或組織中所定義的憑證要求程式，來做到這一點，只要您確定憑證是可匯出的，且包含所有必要的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="eae99-109">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="eae99-110">事先要求憑證是選用的。</span><span class="sxs-lookup"><span data-stu-id="eae99-110">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="eae99-111">如果您未預先要求，您必須在需要憑證的每一部伺服器安裝時，要求他們。</span><span class="sxs-lookup"><span data-stu-id="eae99-111">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="eae99-112">此部署檔提供使用憑證嚮導要求憑證的程式，做為安裝程式的一部分，如在 [lync server 2013 中設定伺服器的憑證](lync-server-2013-configure-certificates-for-servers.md)中所述，在 [lync server 2013 中設定 Director 的憑證](lync-server-2013-configure-certificates-for-the-director.md)，並在此部署檔的 [Lync server 2013 區段中安裝轉送伺服器的](lync-server-2013-install-the-files-for-mediation-server.md) 檔案。</span><span class="sxs-lookup"><span data-stu-id="eae99-112">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="eae99-113">如果您事先要求憑證，則必須在這些區段中修改憑證部署程式，視需要將憑證匯入與指派，而不是在部署時要求。</span><span class="sxs-lookup"><span data-stu-id="eae99-113">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eae99-114">Lync Server 2013 支援 SHA-256 憑證，以用於來自執行 Windows Vista、Windows Server &nbsp; 2008、Windows server &nbsp; 2008 &nbsp; R2 和 Windows 7 作業系統，以及 Lync Phone Edition 之用戶端的連線。</span><span class="sxs-lookup"><span data-stu-id="eae99-114">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="eae99-115">為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。</span><span class="sxs-lookup"><span data-stu-id="eae99-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

