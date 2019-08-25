# Extended FormFields hook interface to Voyager BREAD

This interface extends `VoyagerBaseController::getContentBasedOnType()`, which makes it easy to add data handlers for your own FormFields.

The package includes several additional FormFields:

- **Key-Value to JSON**
- **Multiple Images with tag attributes**

Over time, this list will be updated with new items.

<!-- ## Installation

You can use the artisan command below to install this hook

```bash
php artisan hook:install extended-bread-form-fields
``` -->

### Required
```bash
"laravel/framework": "5.7.*"
"tcg/voyager": "^1.1"
```

## Key-Value to JSON

In BREAD configuration:

![default](https://user-images.githubusercontent.com/2696333/49937836-181a1e00-fee9-11e8-9791-4e347c5e2441.png)

Add new item / Edit item:

![default](https://user-images.githubusercontent.com/2696333/49939862-0b98c400-feef-11e8-9cce-3a0aa003385c.png)

Final Data:

![default](https://user-images.githubusercontent.com/2696333/49937977-7fd06900-fee9-11e8-80ff-d5bf904123f7.png)

## Multiple Images with tag attributes

In BREAD configuration

![image](https://user-images.githubusercontent.com/2696333/50157169-c8b96080-02e1-11e9-9b80-dfa7f7041428.png)

Add new item / Edit item:

![image](https://user-images.githubusercontent.com/2696333/50157243-facac280-02e1-11e9-97ed-e666b10dbe2b.png)

Final Data:

![image](https://user-images.githubusercontent.com/2696333/50157304-25b51680-02e2-11e9-8bca-960f9b2edb07.png)

## MODAL Template Custom

Include in template only:

```bash
    // Add area image
    @foreach($dataType->addRows as $row)
        @if ($row->type === 'multiple_images_with_attrs')
            <div class="form-group">
                <label for="name">{{ $row->display_name }}</label>
                {!! Voyager::formField($row, $dataType, $dataTypeContent) !!}
            </div>
            @break
        @endif
    @endforeach
    <div class="modal fade modal-danger" id="confirm_delete_modal">
        <div class="modal-dialog">
            <div class="modal-content">

                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal"
                            aria-hidden="true">&times;</button>
                    <h4 class="modal-title"><i class="voyager-warning"></i> {{ __('voyager::generic.are_you_sure') }}</h4>
                </div>

                <div class="modal-body">
                    <h4>{{ __('voyager::generic.are_you_sure_delete') }} '<span class="confirm_delete_name"></span>'</h4>
                </div>

                <div class="modal-footer">
                    <button type="button" class="btn btn-default" data-dismiss="modal">{{ __('voyager::generic.cancel') }}</button>
                    <button type="button" class="btn btn-danger" id="confirm_delete">{{ __('voyager::generic.delete_confirm') }}</button>
                </div>
            </div>
        </div>
    </div>
```



