---
layout: post
title: "Type-hinting PHP 7/8"
categories: laravel
---

Besides naming variables properly, you should use type hinting in order to make your code more readable:

eg:

```php
class ReportService {

    public int $projectId;

    public function __construct($projectId)
    {
        $this->projectId = $projectId;
    }

    public function projectReport(): Collection
    {
        return Event::query()
            ->when(!is_null($this->projectId), function($query)) {
                $query->where('project_id', $this->projectId);
            })
            ->get();
    }
}
```
