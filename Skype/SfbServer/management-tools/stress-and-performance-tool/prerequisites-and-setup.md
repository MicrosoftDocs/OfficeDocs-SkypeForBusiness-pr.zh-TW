---
title: Skype 名片壓力與效能工具的先決條件與設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: 商務用 Skype Server 2015 應力和效能工具的需求或先決條件。 如何安裝或設定壓力與效能工具。
ms.openlocfilehash: f52d92022e09314a8f9467cd939f67b2827cc153
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816172"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype 名片壓力與效能工具的先決條件與設定
 
商務用 Skype Server 2015 應力和效能工具的需求或先決條件。 如何安裝或設定壓力與效能工具。
  
我們有下列幾節的硬體、軟體和系統設定需求，您必須先注意，才能執行壓力與效能工具：
  
- [用戶端硬體需求](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [用戶端軟體需求](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [配置需求](prerequisites-and-setup.md#ConfigReqs)
    
此外，我們還提供下列章節，以[安裝商務用 Skype Server 2015 應力和效能工具](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>用戶端硬體需求
<a name="ClientHardwareReqs"> </a>

針對您的商務用 Skype Server 2015 部署執行壓力與效能工具時，您至少需要針對測試中的每個4500使用者符合這些硬體需求：
  
- 1個十億位元網路介面卡
    
- 8 GB RAM
    
- 2個雙核 Cpu
    
## <a name="client-software-requirements"></a>用戶端軟體需求
<a name="ClientSoftwareReqs"> </a>

壓力與效能工具支援的作業系統如下：
  
- Windows Server 2012
    
- Windows Server 2008 （64位）
    
此外，電腦必須符合下列軟體需求：
  
- 您必須安裝 Microsoft .NET 4.5 Framework。 [請在此下載 .Net 4.5 架構。](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- 您將需要在 Windows 中啟用 [桌面體驗] 功能。
    
- 您將需要安裝 Microsoft Visual c + + 2013 （x64）。 [在此下載 Visual c + + 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- 您需要成功部署商務用 Skype Server 2015。
    
## <a name="configuration-requirements"></a>配置需求
<a name="ConfigReqs"> </a>

您必須完成這些額外設定，才能成功執行壓力與效能工具：
  
- 您必須以網域或本機管理員群組的成員身分登入伺服器。
    
- 您無法在使用者帳戶將駐留的任何前端伺服器或標準版伺服器上安裝商務用 Skype Server 2015 使用者建立工具（UserProvisioningTool）。
    
- 當使用者建立工具多次執行時，每個啟用 Microsoft 整合通訊的使用者都必須有唯一的電話號碼。
    
- 頁面檔案大小應由系統管理，或者必須至少為電腦系統中的 RAM 數量的1.5 倍。
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>安裝商務用 Skype Server 2015 應力與效能工具
<a name="Installing"> </a>

安裝可能會比較簡單。 您必須在您要用來模擬使用者流量的每一位用戶端電腦上執行 Windows 安裝程式檔案、 **CapacityPlanningTool**，以及在您要建立使用者和連絡人的每個池中，在前端伺服器上執行。
  
若要下載 .msi，以及其他文章中提及的範例腳本，請移至 [下載中心] 連結：商務用[Skype Server 2015、應力和效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  

