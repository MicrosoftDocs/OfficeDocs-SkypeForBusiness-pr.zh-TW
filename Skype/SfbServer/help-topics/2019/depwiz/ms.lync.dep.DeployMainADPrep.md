---
title: 準備 Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: 若要開始安裝商務用 Skype Server，您必須準備要主控伺服器和使用者之 Active Directory 網域服務架構、樹系和網域。 商務用 Skype Server 部署嚮導會引導您完成準備 Active Directory 所需的步驟（從架構開始，然後再到樹系準備）。 確認 Active Directory 複寫成功後，您就可以準備要主控使用者或伺服器的每個網域。
ms.openlocfilehash: fcc77ed8dab3a6e3e643c2022dc45623e855dfde
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097359"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="ee10c-105">準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="ee10c-105">Prepare Active Directory</span></span>

<span data-ttu-id="ee10c-106">若要開始安裝商務用 Skype Server，您必須準備要主控伺服器和使用者之 Active Directory 網域服務架構、樹系和網域。</span><span class="sxs-lookup"><span data-stu-id="ee10c-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="ee10c-107">商務用 Skype Server 部署嚮導會引導您完成準備 Active Directory 所需的步驟（從架構開始，然後再到樹系準備）。</span><span class="sxs-lookup"><span data-stu-id="ee10c-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="ee10c-108">確認 Active Directory 複寫成功後，您就可以準備要主控使用者或伺服器的每個網域。</span><span class="sxs-lookup"><span data-stu-id="ee10c-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee10c-109">若要順利準備架構，您必須以 Enterprise Admins 群組和 Schema Admins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ee10c-109">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group.</span></span> <span data-ttu-id="ee10c-110">若要準備樹系，您必須以 Enterprise Admins 群組成員的身分登入，或以樹系根管理員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ee10c-110">To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root.</span></span> <span data-ttu-id="ee10c-111">若要進行網域準備，您必須以 Domain Admins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ee10c-111">For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="ee10c-112">如需支援的 Active Directory 拓撲的詳細資訊，請參閱支援檔中的 [Active Directory 支援](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) 。</span><span class="sxs-lookup"><span data-stu-id="ee10c-112">For details about supported Active Directory topologies, see [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in the Supportability documentation.</span></span> <span data-ttu-id="ee10c-113">如需 Active Directory 準備的詳細資訊，請參閱部署檔中的 [Active Directory 網域服務準備工作](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) 。</span><span class="sxs-lookup"><span data-stu-id="ee10c-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in the Deployment documentation.</span></span>