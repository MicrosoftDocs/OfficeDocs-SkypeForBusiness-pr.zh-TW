---
title: Windows PowerShell 和商務用 Skype Server 管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 在商務用 Skype Server 中，管理工具是使用 Windows PowerShell 來執行。 Windows PowerShell 包括命令列環境、產品特有的命令，以及完整的指令碼語言。 使用 Windows PowerShell 所執行商務用 Skype Server 工具組括下列各項：
ms.openlocfilehash: ec70b6acba93d2667f297dd17afc50507aa9e105041195ec7ffa34459fa2b878
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301329"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell 和商務用 Skype Server 管理工具
 
在商務用 Skype Server 中，管理工具是使用 Windows PowerShell 來執行。 Windows PowerShell 包括命令列環境、產品特有的命令，以及完整的指令碼語言。 使用 Windows PowerShell 所執行商務用 Skype Server 工具組括下列各項： 
  
- **拓撲** 產生器。 您可以使用拓撲產生器來建立、調整和發行您規劃的拓撲，並在開始伺服器安裝之前驗證拓撲。 當您在個別伺服器上安裝商務用 Skype Server 時，伺服器會在安裝程式中讀取已發佈的拓撲，而安裝程式會以拓撲中的導向方式來部署伺服器。 設定完成後，設定資訊會自動複寫到所有伺服器。 只有使用拓撲產生器，才能將元件新增至部署。
    
- **商務用 Skype Server 管理命令** 介面。 您可以使用商務用 Skype Server 管理命令介面，以進行部署的完整命令列管理。
    
- **商務用 Skype Server 控制台**。 您可以使用商務用 Skype Server 控制台使用者介面來管理部署中的最常見工作。
    
這些工具使用 Windows PowerShell Cmdlet 來管理您的部署，包含接近550產品特有的 Cmdlet。 商務用 Skype Server 所包含的安全性 Cmdlet 主要是用來管理驗證，以及使用者權利和許可權。 有各種各樣的指令程式可用於管理驗證，包括憑證和個人識別碼 (PIN) 驗證的 Cmdlet。 此外，一些 Cmdlet 可讓您使用新的 Role-Based 存取控制 (RBAC) 功能委派商務用 Skype Server 的管理控制權。 如需商務用 Skype Server Cmdlet 的詳細資訊，請參閱[商務用 Skype Server 管理命令](../../manage/management-shell.md)介面。
  
Windows PowerShell 的腳本安全性功能是專門設計來協助避免舊版技術（包括 Microsoft Visual Basic script Edition (VBScript) ）的腳本相關安全性問題。 Windows PowerShell 的安全性功能主要是用來建立使用者無法輕易或無意中執行腳本的環境。 根據預設，會啟用 Windows PowerShell 安全性功能。 您可以修改這些功能的狀態，以滿足您的腳本需求和各種安全性目標。 這並不是說命令介面讓使用者無法執行腳本。 相反地，命令介面會使使用者在執行腳本時不會有這麼大的難度。 如需詳細資訊，請參閱[Windows PowerShell Script Security](/previous-versions/msdn10/gg261722(v=msdn.10))。
