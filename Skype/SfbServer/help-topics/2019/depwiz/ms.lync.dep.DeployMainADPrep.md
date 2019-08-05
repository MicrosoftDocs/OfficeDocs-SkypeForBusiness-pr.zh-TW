---
title: 準備 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: 若要開始安裝商務用 Skype Server, 您必須準備能主持伺服器與使用者的 Active Directory 網域服務架構、林及網域。 商務用 Skype Server 部署嚮導將引導您完成準備 Active Directory 所需的步驟 (從架構開始, 然後再移至林準備)。 確認 Active Directory 複製成功之後, 您就可以準備每個要主持使用者或伺服器的網域。
ms.openlocfilehash: e4de6019303b53a1828d7ee271194ebca107b0c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187501"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="fa48f-105">準備 Active Directory</span><span class="sxs-lookup"><span data-stu-id="fa48f-105">Prepare Active Directory</span></span>

<span data-ttu-id="fa48f-106">若要開始安裝商務用 Skype Server, 您必須準備能主持伺服器與使用者的 Active Directory 網域服務架構、林及網域。</span><span class="sxs-lookup"><span data-stu-id="fa48f-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="fa48f-107">商務用 Skype Server 部署嚮導將引導您完成準備 Active Directory 所需的步驟 (從架構開始, 然後再移至林準備)。</span><span class="sxs-lookup"><span data-stu-id="fa48f-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="fa48f-108">確認 Active Directory 複製成功之後, 您就可以準備每個要主持使用者或伺服器的網域。</span><span class="sxs-lookup"><span data-stu-id="fa48f-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa48f-p103">若要成功準備架構，您必須以 Enterprise Admins 群組與 Schema Admins 群組成員身分登入。若要準備樹系，您必須以 Enterprise Admins 群組成員身分或是樹系根的系統管理員身分登入。要準備網域，您必須以 Domain Admins 群組成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="fa48f-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="fa48f-p104">如需支援之 Active Directory 拓樸的詳細資訊，請參閱支援文件中的〈[Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)〉。如需 Active Directory 準備的詳細資訊，請參閱部署文件中的〈[Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="fa48f-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


