---
title: 移轉類比裝置
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
description: 商務用 Skype 伺服器提供類比裝置的支援。 具體而言，支援的類比裝置為類比語音電話與類比傳真機。 您可以設定合格的閘道，以支援在商務用 Skype 伺服器環境中使用類比裝置。 遷移至商務用 Skype Server 2019 之後，您還必須遷移與類比裝置相關聯的連絡人物件。 使用商務用 Skype Server 管理命令介面若要先取得與舊版類比裝置相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752825"
---
# <a name="migrate-analog-devices"></a>移轉類比裝置

商務用 Skype 伺服器提供類比裝置的支援。 具體而言，支援的類比裝置為類比語音電話與類比傳真機。 您可以設定合格的閘道，以支援在商務用 Skype 伺服器環境中使用類比裝置。 遷移至商務用 Skype Server 2019 之後，您還必須遷移與類比裝置相關聯的連絡人物件。 使用商務用 Skype Server 管理命令介面若要先取得與舊版類比裝置相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。

### <a name="to-migrate-analog-devices"></a>遷移類比裝置

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [**商務用 skype 伺服器管理命令**介面]。

2. 在命令列中輸入：

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 確認已將所有連絡人物件移至商務用 Skype Server 2019 集區。 在命令列中輸入：

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 確認所有連絡人物件現在已與商務用 Skype Server 2019 集區相關聯。


