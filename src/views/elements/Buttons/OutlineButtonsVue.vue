<template>
    <va-row>
    <div class="col-md-12">
        <va-card theme="primary" :isOutline="true" title="Outline & Block Buttons" icon="fa fa-edit">
            <div slot="content" class="table-responsive">
                <p>Various types of buttons base on vue component. Using the base class <code>.btn</code> with <code>btn-block</code></p>
                <table class="table table-bordered text-center">
                    <tbody>
                    <tr>
                        <th>Normal</th>
                        <th>Large <code>.btn-lg</code></th>
                        <th>Small <code>.btn-sm</code></th>
                        <th>X-Small <code>.btn-xs</code></th>
                        <th>Flat <code>.btn-flat</code></th>
                        <th>Disabled <code>.disabled</code></th>
                    </tr>
                    <tr>
                        <td>
                            <!-- working -->
                            <va-button
                                    name="Primary click"
                                    theme="primary"
                                    :isOutline="true"
                                    :isBlock="true"
                                    @btn-click="$Swal.fire('Basic Alert!')">
                            </va-button>
                        </td>
                        <td>
                            <!-- not working -->
                            <va-button
                                    name="Primary"
                                    theme="primary"
                                    size="lg"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Primary"
                                    theme="primary"
                                    size="sm"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Primary"
                                    theme="primary"
                                    size="xs"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Primary"
                                    theme="primary"
                                    :isFlat="true"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Primary"
                                    theme="primary"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isDisabled="true"
                            ></va-button>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            <va-button
                                    name="Secondary"
                                    theme="secondary"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Secondary"
                                    theme="secondary"
                                    size="lg"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Secondary"
                                    theme="secondary"
                                    size="sm"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Secondary"
                                    theme="secondary"
                                    size="xs"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Secondary"
                                    theme="secondary"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isFlat="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Secondary"
                                    theme="secondary"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isDisabled="true"
                            ></va-button>
                        </td>
                    </tr>

                    <tr>
                        <td>
                            <va-button
                                    name="Success"
                                    theme="success"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Success"
                                    theme="success"
                                    size="btn-lg"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Success"
                                    theme="success"
                                    size="sm"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Success"
                                    theme="success"
                                    size="xs"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Success"
                                    theme="success"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isFlat="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Success"
                                    theme="success"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isDisabled="true"
                            ></va-button>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            <va-button
                                    name="Info"
                                    theme="info"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Info"
                                    theme="info"
                                    size="lg"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Info"
                                    theme="info"
                                    size="sm"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Info"
                                    theme="info"
                                    size="xs"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Info"
                                    theme="info"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isFlat="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Info"
                                    theme="info"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isDisabled="true"
                            ></va-button>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            <va-button
                                    name="Danger"
                                    theme="danger"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Danger"
                                    theme="danger"
                                    size="lg"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Danger"
                                    theme="danger"
                                    size="sm"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Danger"
                                    theme="danger"
                                    size="xs"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Danger"
                                    theme="danger"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isFlat="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Danger"
                                    theme="danger"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isDisabled="true"
                            ></va-button>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            <va-button
                                    name="Warning"
                                    theme="warning"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Warning"
                                    theme="warning"
                                    size="lg"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Warning"
                                    theme="warning"
                                    size="sm"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Warning"
                                    theme="warning"
                                    size="xs"
                                    :isOutline="true"
                                    :isBlock="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Warning"
                                    theme="warning"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isFlat="true"
                            ></va-button>
                        </td>
                        <td>
                            <va-button
                                    name="Warning"
                                    theme="warning"
                                    :isOutline="true"
                                    :isBlock="true"
                                    :isDisabled="true"
                            ></va-button>
                        </td>
                    </tr>
                    </tbody>
                </table>
            </div>
        </va-card>
    </div>
</va-row>
</template>

<script>
    export default {
        name: "ButtonsVue",
    }
</script>

