---
title: 自訂商務用 Skype Server 中的 Windows 用戶端安裝
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 摘要：商務用 Skype 安裝方法及工具的概述。
ms.openlocfilehash: ba859ba9aa73b69caa471d698a9980719ba6cdea
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773343"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a>自訂商務用 Skype Server 中的 Windows 用戶端安裝
 
**摘要：** 商務用 Skype 的安裝方法及工具的概述。
  
> [!NOTE]
> 如需 Microsoft 365 和 Office 365 隨附之商務用 Skype 的安裝資訊，請參閱[在 Microsoft 365 或 Office 365 中部署商務用 Skype 用戶端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。 
  
Enterprise 管理員可以使用本節所述的方法，來自訂 Windows 安裝程式型 (.msi) 安裝大量授權版本的商務用 Skype。 因為沒有單一工具提供所有自訂選項，所以您可能在商務用 Skype 部署中使用這些方法的組合。 您可以使用下列各節所述的工具：
  
- [使用商務用 Skype Server 的 Office 自訂工具 (OCT) ](use-the-office-customization-tool-oct.md)自訂商務用 Skype 和其他 Office 程式的安裝程式選項及功能。
    
- [使用 Config.xml 在商務用 Skype Server 中執行安裝](use-config-xml-to-perform-installation-tasks.md)工作，以指定網路安裝點的路徑，並執行無訊息安裝。
    
- [使用商務用 Skype Server 中的安裝程式命令列選項](use-setup-command-line-options.md)，指定要在安裝期間使用的 Config.xml 檔案。
    
- 使用群組原則物件編輯器 MMC 嵌入式管理單元，[設定商務用 Skype Server 中的用戶端引導原則](configure-client-bootstrapping-policies.md)。
    
當您部署 Office 套件時，可能會有其他的選項需要加以設定。 本節中的主題概要說明這些自訂工具，並討論商務用 Skype 的相關考慮。 包含的連結為每個工具的詳細 Office 說明。 
  

