---
title: 商務用 Skype Server 控制台的第一次執行檢查清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: 歡迎使用商務用 Skype Server 控制台，以 web 為基礎的使用者介面，用來管理和管理商務用 Skype Server。 您可以使用 [控制台] 執行先前版本中使用 Microsoft 管理主控台所執行的系統管理工作類型。
ms.openlocfilehash: fdd6aeefb6c4914dec54673f426c95c4028388ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836623"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>商務用 Skype Server 控制台的第一次執行檢查清單

歡迎使用商務用 Skype Server 控制台，以 web 為基礎的使用者介面，用來管理和管理商務用 Skype Server。 您可以使用 [控制台] 執行先前版本中使用 Microsoft 管理主控台所執行的系統管理工作類型。

在您部署商務用 Skype Server 之後，我們強烈建議您執行一些重要工作。 這些工作中，一部份是初始設定步驟，您可能已在部署期間執行過，但其他的則是針對您在部署期間的設定或是預設設定進行細分或修改。 本主題中描述的其他工作會驗證您在部署過程中所進行的設定。

> [!NOTE]
> 在執行下表中的工作之前，請務必使用「 [Role-Based 存取控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) 」主題中的「角色與範圍」一節所述的正確使用者權限、許可權和角色進行登入。

## <a name="first-run-checklist"></a>第一次執行檢查清單

強烈建議您複查本主題中所述的工作，然後在您的組織中執行適當的部署程式。

|**工作**|**控制台群組**|**文件**|
|:-----|:-----|:-----|
|確認您安裝在拓撲中的服務如預期地執行中。  <br/> |**拓撲** <br/> |[查看服務的詳細資料](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|為使用者啟用商務用 Skype Server。 （選用）從先前版本遷移時，將使用者移至商務用 Skype Server。  <br/> |**使用者** <br/> |[管理使用者](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|如果您已部署，或想要部署 Enterprise Voice，請設定 SIP 主幹連線，以啟用對公用交換電話網路 (PSTN) 的連線。  <br/> |**語音路由** <br/> |[設定主幹和轉譯規則](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|如果您部署了 Enterprise Voice，請確認 Enterprise Voice 路由設定。  <br/> |**語音路由** <br/> |[測試語音路由](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|如果您部署了封存伺服器，請確認封存原則和設定符合您組織的規範需要。  <br/> |**監控和封存** <br/> |[管理封存](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|如果您部署了監控伺服器，請檢視監控伺服器報告，以便檢視使用方式和診斷資訊。  <br/> |**首頁** <br/> |[在商務用 Skype Server 中管理健康情況與監控](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


