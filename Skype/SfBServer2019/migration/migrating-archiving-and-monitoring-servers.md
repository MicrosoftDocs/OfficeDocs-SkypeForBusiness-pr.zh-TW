---
title: 遷移封存與監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果您在舊版環境中部署了 [封存伺服器] 和 [監視伺服器]，您可以在您遷移前端池之後，將這些伺服器部署在商務用 Skype Server 2019 環境中。 不過，如果封存和監控功能對您的組織而言是至關重要的，您應該先在您的商務用 Skype Server 2019 試驗區中新增封存與監控，以便在遷移程式中提供此功能。
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813451"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>遷移封存與監控伺服器

如果您在舊版環境中部署了 [封存伺服器] 和 [監視伺服器]，您可以在您遷移前端池之後，將這些伺服器部署在商務用 Skype Server 2019 環境中。 不過，如果封存和監控功能對您的組織而言是至關重要的，您應該先在您的商務用 Skype Server 2019 試驗區中新增封存與監控，以便在遷移程式中提供此功能。 
  
如果您想要在遷移期間進行封存與監控，請記住下列考慮事項：
  
- 歸檔資料和監控資料不會移至商務用 Skype Server 2019 部署。 您在解除舊版環境之前備份的資料將是舊版環境中的活動歷程記錄。
    
- 舊版本的 [封存伺服器] 和 [監視伺服器] 只能與舊版的 [前端] 池相關聯。 在商務用 Skype Server 2019 中，[封存及監視] 不再是伺服器角色，但是整合到商務用 Skype Server 2019 前端的服務。
    
- 在舊版及商務用 Skype Server 2019 部署期間共存時，舊版的存檔伺服器與監視伺服器會針對駐留在舊版池中的使用者收集資料。 商務用 Skype Server 2019 中的 [封存與監控] 可收集駐留在商務用 Skype Server 2019 池的使用者資料。
    
    > [!NOTE]
    > 在遷移階段，當您仍將舊版 Edge 伺服器與新的商務用 Skype Server 2019 （試用版池）結合使用時，舊版本的封存伺服器會繼續收集駐留在舊版池中的使用者資料，並在商務用 Skype 中進行歸檔伺服器2019會收集駐留在商務用 Skype Server 2019 池的使用者資料。 
  
- 如果您在商務用 Skype Server 2019 的 [封存與監控] 中使用協力廠商的歸檔與監控解決方案，請諮詢您的供應商，以瞭解何時以及如何將協力廠商解決方案與商務用 Skype Server 2019 整合。
    

