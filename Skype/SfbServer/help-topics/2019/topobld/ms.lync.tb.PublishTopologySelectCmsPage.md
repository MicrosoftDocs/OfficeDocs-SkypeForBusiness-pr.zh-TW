---
title: 發行拓撲選取 CMS 頁面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用拓撲產生器，發佈已設定的拓撲。 系統會要求您從清單中選取前端伺服器或前端集區，以擔當存放中央管理存放區的角色。 在任何指定時間，只有一部前端伺服器或前端集區可以持有此角色。
ms.openlocfilehash: 91dd8d9c5fc6bc0fa34d76a77ee487393310e3e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629835"
---
# <a name="publish-topology-select-cms-page"></a>發行拓撲選取 CMS 頁面
 
您可以使用拓撲產生器，發佈已設定的拓撲。 系統會要求您從清單中選取前端伺服器或前端集區，以擔當存放中央管理存放區的角色。 在任何指定時間，只有一部前端伺服器或前端集區可以持有此角色。 
  
### <a name="about-the-central-management-server"></a>關於中央管理伺服器
中央管理伺服器是單一主/多個複本系統，其中包含中央管理伺服器的前端伺服器會持有資料庫的讀/寫副本。 拓撲中的每一部電腦（包括包含中央管理伺服器的前端伺服器）在安裝和部署期間，) 安裝于電腦上的 SQL Server 資料庫 (中，都有中央管理存放區資料的唯讀副本。 本機資料庫會透過 Lync Server 複本複製器代理程式，以在所有電腦上執行為服務的方式接收復本更新。 中央管理伺服器及本機複本上之實際資料庫的名稱是 XDS，這是由 XDS 及 XDS 檔所組成。 Master 資料庫位置是由 Active Directory 網域服務中 (SCP) 的服務控制點所參照。 所有使用中央管理伺服器來管理及設定 Lync Server 的工具，都使用 SCP 來尋找中央管理存放區。
  
## <a name="see-also"></a>另請參閱

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)