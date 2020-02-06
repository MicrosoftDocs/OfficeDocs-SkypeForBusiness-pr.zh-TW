---
title: 發行拓撲選取 CMS 頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用 [拓撲建立器] 發佈已設定的拓撲。 系統會要求您從清單中選取前端伺服器或前端池將會擔任中央管理儲存區的角色。 在任何指定時間，只有一個前端伺服器或前端池可以擁有此角色。
ms.openlocfilehash: cae0f79b9787458ae1dd24077dfdd46689378414
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795414"
---
# <a name="publish-topology-select-cms-page"></a>發行拓撲選取 CMS 頁面
 
您可以使用 [拓撲建立器] 發佈已設定的拓撲。 系統會要求您從清單中選取前端伺服器或前端池將會擔任中央管理儲存區的角色。 在任何指定時間，只有一個前端伺服器或前端池可以擁有此角色。 
  
### <a name="about-the-central-management-server"></a>關於中央管理伺服器
[中央管理伺服器] 是單一主要/多重複本系統，其中資料庫的讀/寫複本是由包含中央管理伺服器的前端伺服器所保留。 拓朴中的每個電腦（包括包含中央管理伺服器的前端伺服器）在安裝期間都有在電腦上安裝的 SQL Server 資料庫中的中央管理儲存資料（預設為 RTCLOCAL）的唯讀複本部署. 本機資料庫會按照 Lync Server 複本複製器代理程式（在所有電腦上以服務形式執行）的方式來接收復制副本更新。 中央管理伺服器上的實際資料庫名稱與局部複本是 XDS，這是由 XDS 和 XDS 檔案組成。 主資料庫位置是由 Active Directory 網域服務中的服務控制點（SCP）所參照。 所有使用中央管理伺服器來管理和設定 Lync Server 的工具，都使用 SCP 來尋找中央管理儲存區。
  
## <a name="see-also"></a>另請參閱

[移動流覽 CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
