---
title: 安裝本機組態存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 若要開始安裝新的商務用 Skype Server 角色服務器，您必須先安裝將主控本機設定存放區的本機 SQL Server。 本機設定存放區將充當商務用 Skype Server 中央管理存放區的唯讀複本 (CMS) 。
ms.openlocfilehash: 78492f8ce913d8f73336ae4f6cdf06fd340ed5f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095977"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="15abc-104">安裝本機組態存放區</span><span class="sxs-lookup"><span data-stu-id="15abc-104">Install Local Configuration Store</span></span>

<span data-ttu-id="15abc-105">若要開始安裝新的商務用 Skype Server 角色服務器，您必須先安裝將主控本機設定存放區的本機 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="15abc-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="15abc-106">本機設定存放區將充當商務用 Skype Server 中央管理存放區的唯讀複本 (CMS) 。</span><span class="sxs-lookup"><span data-stu-id="15abc-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="15abc-107">您必須以電腦的本機系統管理員身分登入您執行 **[安裝本機設定存放區]** 步驟的伺服器，且擁有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="15abc-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="15abc-108">如果您在 Edge Server 上執行安裝程式，則您不必是 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="15abc-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="15abc-109">拓撲產生器定義檔會從匯出的定義檔讀取，而不是從中央管理存放區讀取。</span><span class="sxs-lookup"><span data-stu-id="15abc-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="15abc-110">若要匯出拓撲產生器定義檔，並將其提供給 Edge Server，請參閱[匯出拓撲及將其複製到 Edge 安裝的外部媒體](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)主題。</span><span class="sxs-lookup"><span data-stu-id="15abc-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="15abc-111">若要開始安裝：</span><span class="sxs-lookup"><span data-stu-id="15abc-111">To begin the installation:</span></span>

1. <span data-ttu-id="15abc-112">在 [商務用 Skype 伺服器] 頁面上，按一下 [ **步驟1：安裝本機設定存放區**] 旁邊的 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="15abc-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="15abc-113">在 [ **本機伺服器** 設定] 頁面上，確定已選取 [ **自動從中央管理存放區取得** 設定] 選項，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="15abc-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="15abc-114">當本機伺服器設定安裝完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="15abc-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="15abc-115">安裝本機 SQL Server 可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="15abc-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="15abc-116">安裝 SQL Server 時，將不會在安裝摘要畫面上看到進行中的更新。</span><span class="sxs-lookup"><span data-stu-id="15abc-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="15abc-117">如果您想要監視安裝進度，請使用 [工作管理員] 來觀賞 SQL Server 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="15abc-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>