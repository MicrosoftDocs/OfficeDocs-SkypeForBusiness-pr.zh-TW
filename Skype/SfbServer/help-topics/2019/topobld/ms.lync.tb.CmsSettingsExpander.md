---
title: CMS 設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.CmsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4b882923-ed6f-44f3-ad9c-aabad5a3bc00
ROBOTS: NOINDEX, NOFOLLOW
description: 中央管理伺服器的位置可以從一個已定義的前端集區變更到另一個已定義的前端集區。 若要變更中央管理伺服器的位置，請從 [要安裝中央管理伺服器的前端伺服器] 下的下拉式清單中，選取前端集區。 前端伺服器可以是 Enterprise Edition 前端集區或 Standard Edition 前端伺服器。
ms.openlocfilehash: f0a2539496f10660195790b1168fd08c28ba5263
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120006"
---
# <a name="cms-settings-expander"></a><span data-ttu-id="8cd24-105">CMS 設定展開工具</span><span class="sxs-lookup"><span data-stu-id="8cd24-105">CMS Settings Expander</span></span>
 
<span data-ttu-id="8cd24-p102">中央管理伺服器的位置可以從一個已定義的前端集區變更到另一個已定義的前端集區。若要變更中央管理伺服器的位置，請從 [要安裝中央管理伺服器的前端伺服器] 下的下拉式清單中，選取前端集區。前端伺服器可以是 Enterprise Edition 前端集區或 Standard Edition 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="8cd24-p102">The Central Management Server can be changed from one defined Front End pool to another defined Front End pool. To change the location of the Central Management Server, select the Front End pool from the drop-down list under **Front End server to install Central Management Server on**. A Front End Server can be an Enterprise Edition Front End pool or a Standard Edition Front End Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8cd24-109">如果您已定義、發行及部署基礎結構的中央管理存放區，則必須以外部程序將中央管理存放區重新放置到另一個前端，才能變更中央管理存放區的位置。</span><span class="sxs-lookup"><span data-stu-id="8cd24-109">If you have defined, published, and deployed the Central Management store for the infrastructure, you cannot change the location of the Central Management store without relocating the Central Management store to another Front End by an external process.</span></span> 
  
<span data-ttu-id="8cd24-110">如需移動中央管理伺服器存放區的詳細資訊，請參閱 Windows PowerShell Cmdlet 參考中的 [Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="8cd24-110">For details about moving the Central Management Server store, see [Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps) in the Windows PowerShell cmdlet reference.</span></span>
