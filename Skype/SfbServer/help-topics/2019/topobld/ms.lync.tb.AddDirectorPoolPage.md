---
title: 新增 Director 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定義控制器池 FQDN，請選取多個電腦池，其中包含負載平衡池中的兩個或多個控制器，或是單一電腦池。 您也必須輸入要用來連線到主管池或單一控制器 FQDN 的完整功能變數名稱（FQDN）。 對於控制器電腦池，這會是硬體負載平衡器之虛擬 IP 的網域名稱系統（DNS）專案，或是 DNS 負載平衡的共用 DNS 專案。
ms.openlocfilehash: 491d50c733314e1811aac38c556a6d4683b6956b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796572"
---
# <a name="add-director-pool"></a>新增 Director 集區
 
若要**定義控制器池 FQDN**，請選取**多個電腦池**，其中包含負載平衡池中的兩個或多個控制器，或是**單一電腦池**。 您也必須輸入要用來連線到主管池或單一控制器 FQDN 的完整功能變數名稱（FQDN）。 對於控制器電腦池，這會是硬體負載平衡器之虛擬 IP 的網域名稱系統（DNS）專案，或是 DNS 負載平衡的共用 DNS 專案。
  
> [!TIP]
> 如果您打算在將來實施控制器池，請選取 [**多個電腦池**]。 即使某個池已定義為兩個以上的負載平衡電腦，您也可以建立單一電腦池，並為單一電腦建立一個池 FQDN。 當您準備好要稍後再新增更多電腦至池中時，您必須再次執行拓撲建立器，以定義新的池成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導來設定新的控制器池成員。 您也必須將新的池成員新增到該池的適當負載平衡器、[網域名稱系統（DNS）負載平衡] 或 [硬體負載平衡器]。 在許多情況下，系統會同時進行兩個負載平衡系統。 請確定您要將新的成員伺服器新增到兩者中。 
  

