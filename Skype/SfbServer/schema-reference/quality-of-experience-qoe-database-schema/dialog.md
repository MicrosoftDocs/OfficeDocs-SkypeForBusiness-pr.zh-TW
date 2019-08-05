---
title: Dialog 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定 (SIP)] 對話方塊。
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192676"
---
# <a name="dialog-table"></a>Dialog 表格
 
對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定 (SIP)] 對話方塊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |優質 (QoE) 代理程式從來電者或被叫方接收到第一個報告的時間。 與 SessionSeq 搭配使用, 可唯一識別會話。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |[順序編號] 可在有相同 ConferenceDateTime 的情況下區分會話。  <br/> |
|**DialogID** <br/> |Varchar (256)  <br/> ||全域唯一的對話方塊識別碼。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |對話方塊識別碼的校驗和。  <br/> |
   

