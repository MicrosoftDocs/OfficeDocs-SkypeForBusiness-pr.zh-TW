---
title: 移除舊版封存和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果舊版部署包含封存伺服器或監控伺服器，在遷移至商務用 Skype Server 2019 後，只要所有使用者都已從其餘的舊版集區中移除，這些伺服器便可以從舊版環境中移除。 您可以依任何順序移除封存伺服器或監控伺服器。 重要的一點是，所有的使用者都已經從其他的舊版集區中移除。
ms.openlocfilehash: 204c68a50585bae033149ea75077ab0801b0bcc4aecb642c52fa96442bfc42ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304715"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a>移除舊版封存和監控伺服器

如果舊版部署包含封存伺服器或監控伺服器，在遷移至商務用 Skype Server 2019 之後，就可以從舊版環境中移除這些伺服器，只要所有使用者都已從其他的舊版集區中移除。 您可以依任何順序移除封存伺服器或監控伺服器。 重要的一點是，所有的使用者都已經從其他的舊版集區中移除。
  
您可以遵循[階段4：將測試使用者移至試驗集](phase-4-move-test-users-to-the-pilot-pool.md)區中所述的程式，將使用者移至商務用 Skype Server 2019。
  
確認所有使用者都已從任何剩餘的集區中移除之後，請 decommision 伺服器並移除角色。 不過，已過期，但相關的範例是「卸載 Microsoft Lync Server 並移除伺服器角色」，其可在這裡下載 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) 。
  

