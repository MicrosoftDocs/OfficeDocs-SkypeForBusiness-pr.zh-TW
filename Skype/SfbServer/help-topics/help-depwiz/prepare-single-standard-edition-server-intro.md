---
title: 準備單一 Standard Edition Server (簡介)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 若要開始安裝商務用 Skype Server 2015 標準版伺服器，而該伺服器會保留中央管理儲存區及您所選取的其他 collocated 服務，您必須以本機管理員群組的成員身分登入，該伺服器將成為標準版伺服器。 [準備單一 Standard Edition Server] 頁面詳述初始安裝的需求。 該電腦必須是您要部署的所屬網域成員，且您必須為您的樹系成功完成架構、樹系及網域準備工作。
ms.openlocfilehash: ed7c353f602d97842e654faa5b539a6dcae01133
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687346"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="c27b8-105">準備單一 Standard Edition Server (簡介)</span><span class="sxs-lookup"><span data-stu-id="c27b8-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="c27b8-106">若要開始安裝商務用 Skype Server 2015 標準版伺服器，而該伺服器會保留中央管理儲存區及您所選取的其他 collocated 服務，您必須以本機管理員群組的成員身分登入，該伺服器將成為標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="c27b8-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="c27b8-107">[準備單一 Standard Edition Server]\*\*\*\* 頁面詳述初始安裝的需求。</span><span class="sxs-lookup"><span data-stu-id="c27b8-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="c27b8-108">該電腦必須是您要部署的所屬網域成員，且您必須為您的樹系成功完成架構、樹系及網域準備工作。</span><span class="sxs-lookup"><span data-stu-id="c27b8-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="c27b8-109">此項特殊工作是專門用來安裝 Standard Edition 伺服器以作為基礎結構中第一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="c27b8-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="c27b8-110">此工作會將中央管理儲存區（即 SQL Server Express）安裝到標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="c27b8-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="c27b8-111">如果您已經部署了另一部 Standard Edition 伺服器或前端集區，則請按一下 [取消]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c27b8-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c27b8-112">完成這項工作之後，您將會安裝拓撲建立器（如果尚未安裝），並設定您的拓撲檔。</span><span class="sxs-lookup"><span data-stu-id="c27b8-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="c27b8-113">您必須要有可用的中央管理存放區 (完成此主題中說明的工作來部署)，才能發行拓樸文件。</span><span class="sxs-lookup"><span data-stu-id="c27b8-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

