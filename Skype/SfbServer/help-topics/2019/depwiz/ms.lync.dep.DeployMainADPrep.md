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
ms.openlocfilehash: 4e2951643ddc0f569df6802b6ff5fdd8d2c12a82
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825045"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="b1a3b-105">準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="b1a3b-105">Prepare Active Directory</span></span>

<span data-ttu-id="b1a3b-106">若要開始安裝商務用 Skype Server，您必須準備要主控伺服器和使用者之 Active Directory 網域服務架構、樹系和網域。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="b1a3b-107">商務用 Skype Server 部署嚮導會引導您完成準備 Active Directory 所需的步驟（從架構開始，然後再到樹系準備）。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="b1a3b-108">確認 Active Directory 複寫成功後，您就可以準備要主控使用者或伺服器的每個網域。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1a3b-109">若要順利準備架構，您必須以 Enterprise Admins 群組和 Schema Admins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-109">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group.</span></span> <span data-ttu-id="b1a3b-110">若要準備樹系，您必須以 Enterprise Admins 群組成員的身分登入，或以樹系根管理員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-110">To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root.</span></span> <span data-ttu-id="b1a3b-111">若要進行網域準備，您必須以 Domain Admins 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-111">For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="b1a3b-112">如需支援的 Active Directory 拓撲的詳細資訊，請參閱支援檔中的 [Active Directory 支援](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="b1a3b-113">如需 Active Directory 準備的詳細資訊，請參閱部署檔中的 [Active Directory 網域服務準備工作](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


