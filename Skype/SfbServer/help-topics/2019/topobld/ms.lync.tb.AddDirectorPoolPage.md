---
title: 新增 Director 集區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 若要定義 Director 集區 FQDN，請選取要包含在負載平衡集區中的兩個或多個 Director 或單一電腦集區的多部電腦集區。 您也必須輸入要用來連接 Director 集區的完整功能變數名稱 (FQDN) 或單一 Director 的 FQDN。 針對 Director 電腦的集區，這會是網域名稱系統 (DNS) 專案，以供硬體負載平衡器的虛擬 IP 或 DNS 負載平衡的共用 DNS 專案使用。
ms.openlocfilehash: 910ed1cee56a9a7dab395496ec1ce02f91bc2a5f00f8cbb4d8032b4170263854
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338561"
---
# <a name="add-director-pool"></a>新增 Director 集區
 
若要 **定義 Director 集區 FQDN**，請選取要包含在負載平衡集區中的兩個或多個 Director 或 **單一電腦集** 區的 **多部電腦集** 區。 您也必須輸入要用來連接 Director 集區的完整功能變數名稱 (FQDN) 或單一 Director 的 FQDN。 針對 Director 電腦的集區，這會是網域名稱系統 (DNS) 專案，以供硬體負載平衡器的虛擬 IP 或 DNS 負載平衡的共用 DNS 專案使用。
  
> [!TIP]
> 如果您打算未來實作 Director 集區，請選取 [多部電腦集區]。 即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。 當您準備好將更多電腦新增至集區之後，您必須再次執行拓撲產生器以定義新的集區成員、發佈新的拓撲，然後透過「商務用 Skype Server 部署」嚮導設定新的 Director 集區成員。 您也必須新增集區成員至集區的適當負載平衡器、網域名稱系統 (DNS) 負載平衡或硬體負載平衡器。 在許多情況下，您會同時具有兩種負載平衡系統。 請務必將新成員伺服器同時新增到這兩種系統。 
  

